# Documento de Especificación de Requisitos (Requirements Document)

## Resumen de Análisis de Intención (Intent Analysis Summary)
- **Solicitud del Usuario**: Aplicar el framework AI-DLC siguiendo `Contexto_mejoras.md`, `logo_vectorial_herrefinance_svg.md` y `gu_a_de_marca_y_estrategia_visual.md` para ajustar los logotipos del portafolio. Como esta es la página principal de Luis Felipe Herreño (Pipe Herre), el símbolo dentro de la gorra debe ser `{/}`.
- **Tipo de Solicitud**: Refactorización estética, integración de identidad de marca (Branding) y optimización de arquitectura frontend.
- **Estimación de Alcance**: A nivel de sistema (Navbar, Favicon, Hero, Footer, CSS global y componentes principales).
- **Estimación de Complejidad**: Moderada (diseño vectorial SVG de precisión, normalización de tokens CSS y preservación de arquitectura estática sin backend).
- **Profundidad de Requisitos**: Estándar adaptativa (Standard Depth).

---

## Decisiones Clave de Clarificación

| ID Pregunta | Tema | Decisión del Usuario | Justificación Técnica |
| :--- | :--- | :--- | :--- |
| **Q1** | Extensión de Seguridad | **No (Omitir)** | Adecuado para un portafolio estático generado con SSG sin almacenamiento de credenciales ni APIs backend activas. |
| **Q2** | Ubicación Isotipo Gorra `{/}` | **Navbar, Favicon, Footer y Hero** | Proporciona coherencia de marca integral: pestaña del navegador, cabecera de navegación, cierre en pie de página y elemento gráfico distintivo en la portada. |
| **Q3** | Acento de Color | **Azul Eléctrico / Cyan Arquitecto (`#38BDF8`)** | Refleja especialización en arquitectura cloud y backend, manteniendo sinergia con el Universo Herre y reservando el verde mint para submarcas financieras como Herrefinance. |
| **Q4** | Alcance de Mejoras | **Refactorización estética y de identidad completa** | Adopción de la gorra `{/}`, normalización de variables CSS (eliminando duplicados), depuración de deuda técnica y elevación de jerarquía visual en componentes clave. |

---

## Requisitos Funcionales (Functional Requirements)

### FR-01: Componente Isotipo Vectorial de la Gorra `{/}`
- **Descripción**: Crear un componente SVG reutilizable y responsive que renderice la silueta vectorial de la gorra de programador descrita en `gu_a_de_marca_y_estrategia_visual.md`, conteniendo en su centro el glifo `{/}` con tipografía monospace nítida.
- **Criterios de Aceptación**:
  - Trazos vectoriales limpios (visera, domo con degradado sutil, botón superior y ribete).
  - El glifo `{/}` debe lucir centrado, legible y con acento Cyan Arquitecto (`#38BDF8`).
  - Debe escalar nítidamente sin deformarse tanto en tamaños miniatura (32px-48px) como en display amplio.

### FR-02: Actualización de Marca en Navbar
- **Descripción**: Integrar el isotipo de la gorra `{/}` junto al texto de marca en `src/components/Navbar.astro`.
- **Criterios de Aceptación**:
  - Disposición horizontal armónica: Isotipo a la izquierda + texto `PIPEHERRE` (o `LUIS FELIPE HERREÑO`) con jerarquía tipográfica limpia.
  - Enlace funcional hacia la raíz del sitio o `#hero`.
  - Adaptabilidad fluida en vistas móvil y escritorio sin romper el botón del menú hamburguesa.

### FR-03: Actualización de Favicons del Navegador
- **Descripción**: Generar e implementar `favicon.svg` y versiones de respaldo en `public/` con el isotipo de la gorra `{/}` dentro de un contenedor squircle/redondeado optimizado para pestañas en temas claros y oscuros.
- **Criterios de Aceptación**:
  - Reemplazo completo del favicon anterior en `public/favicon.svg`.
  - Excelente legibilidad en la pestaña del navegador a 16x16 y 32x32 píxeles.

### FR-04: Firma de Marca en Footer (`Contact.astro`)
- **Descripción**: Actualizar el pie de página en `Contact.astro` para incorporar el isotipo de la gorra `{/}` acompañado del texto institucional de la marca personal y los créditos de autor.
- **Criterios de Aceptación**:
  - Reemplazo del texto plano actual por un layout elegante con el isotipo de la gorra y copyright actualizado.

### FR-05: Integración Gráfica en Sección Hero (`Hero.astro`)
- **Descripción**: Incorporar un elemento gráfico de marca sutil o badge enriquecido con el isotipo `{/}` en la portada para reforzar la identidad de Arquitecto de Software / Technical Lead.
- **Criterios de Aceptación**:
  - Integración armónica en la tarjeta de perfil o en el encabezado sin sobrecargar la composición visual.

### FR-06: Normalización del Design System en `global.css`
- **Descripción**: Limpiar y consolidar las variables de diseño en `:root` de `src/styles/global.css`, eliminando definiciones duplicadas y configurando los tokens oficiales del Universo Herre (fondo `#0D1117`, superficie `#161B22`, texto `#F0F6FC`, acento `#38BDF8`, bordes sutiles).
- **Criterios de Aceptación**:
  - Cero variables duplicadas en `:root`.
  - Paleta armonizada con alto contraste y consistencia visual a lo largo de todas las secciones.

### FR-07: Refinamiento de Componentes Clave
- **Descripción**: Elevar la jerarquía visual, espaciados y legibilidad de `Hero.astro`, `Experience.astro` y `Projects.astro` respetando el contenido real y los enlaces existentes sin inventar datos profesionales.
- **Criterios de Aceptación**:
  - Mejor lectura en dispositivos móviles.
  - Tipografía afinada con contraste accesible (WCAG AA).

---

## Requisitos No Funcionales (Non-Functional Requirements)

### NFR-01: Rendimiento y Arquitectura Estática (Performance & SSG)
- La aplicación debe mantenerse 100% estática (Static Site Generation con Astro). Cero JavaScript innecesario en tiempo de carga inicial.
- Tiempo de carga percibido inmediato y renderizado sin bloqueos.

### NFR-02: Estética Visual Premium (Visual Polish)
- Diseño moderno, sobrio y profesional que proyecte seniority y criterio técnico (evitando plantillas genéricas).
- Efectos de micro-interacciones sutiles (hover en botones, transiciones de scroll suaves y backdrop-filter nítidos).

### NFR-03: Responsividad (Responsive Web Design)
- Experiencia visual y táctil perfectamente adaptada desde pantallas móviles pequeñas (360px) hasta monitores 4K.

### NFR-04: Accesibilidad (a11y)
- Contraste de texto y elementos interactivos acorde con las pautas WCAG 2.1 nivel AA.
- Atributos semánticos `aria-label`, `aria-hidden` y textos alternativos precisos en imágenes y SVGs.

### NFR-05: Simplicidad y Mantenibilidad (Maintainability)
- Cero dependencias adicionales en `package.json`.
- Estructura de código comprensible, modular y fácil de mantener por cualquier desarrollador.
- Respeto total al principio de no sobreingeniería establecido en `Contexto_mejoras.md`.
