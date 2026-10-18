# Inventario de Componentes (Component Inventory)

## Componentes de la Aplicación (Application Components)
1. **`Navbar.astro`**: Barra de cabecera con logotipo, menú principal para pantallas grandes y menú lateral/desplegable para dispositivos móviles.
2. **`Hero.astro`**: Sección de bienvenida e impacto visual inicial, con titular, subtítulo, tecnologías destacadas, botones de acción y fotografía profesional enmarcada.
3. **`LinkedInPosts.astro`**: Sección dedicada a mostrar publicaciones técnicas de LinkedIn en formato de tarjetas con imágenes y enlaces directos.
4. **`About.astro`**: Sección de presentación personal y profesional, destacando la visión sobre arquitectura de software y etiquetas de competencias.
5. **`Experience.astro`**: Cronología de experiencia profesional con roles, empresas, contextos de negocio (BRE-B), logros clave y stacks técnicos.
6. **`Projects.astro`**: Muestra de proyectos destacados y laboratorios de arquitectura con tarjetas informativas.
7. **`Architecture.astro`**: Presentación en cuadrícula de los 6 principios de diseño de sistemas que guían la toma de decisiones técnicas.
8. **`Contact.astro`**: Sección de cierre con llamado a la acción para networking, enlaces de contacto directo y footer con derechos de autor.
9. **`SocialRail.astro`**: Barra flotante persistente con enlaces rápidos a perfiles sociales (LinkedIn, GitHub).

---

## Componentes de Estructura y Plantilla
1. **`Layout.astro`**: Componente de diseño base que contiene la estructura HTML, encabezados `<head>`, fuentes tipográficas, metadatos y observadores de intersección.
2. **`index.astro`**: Página principal que agrupa y organiza todos los componentes de la aplicación.

---

## Archivos de Configuración e Infraestructura
1. **`package.json`**: Declaración de dependencias del proyecto, metadatos y scripts ejecutables.
2. **`package-lock.json`**: Árbol determinista de dependencias instaladas.
3. **`astro.config.mjs`**: Configuración de Astro.
4. **`tsconfig.json`**: Configuración de compilación de TypeScript para Astro.

---

## Recursos Compartidos y Estilos (Shared Assets & Styles)
1. **`src/styles/global.css`**: Hoja de estilos globales con variables CSS personalizadas y reglas base.
2. **`public/favicon.svg`**: Icono SVG de la aplicación para navegadores.
3. **`public/favicon.ico`**: Favicon estándar para compatibilidad.
4. **`public/images/`**: Directorio de almacenamiento para imágenes de publicaciones (`.jfif`) y foto de perfil (`.jpeg`).

---

## Conteo Total (Total Count)
- **Total de Componentes Astro (`src/components/`)**: 9
- **Total de Layouts (`src/layouts/`)**: 1
- **Total de Páginas (`src/pages/`)**: 1
- **Total de Hojas de Estilos Globales**: 1
- **Total de Archivos de Configuración**: 4
- **Total de Recursos Multimedia (`public/`)**: 8 (6 imágenes + 2 favicons)
- **Total de Componentes / Módulos de Código Fuente**: 11 archivos `.astro` + 1 `.css` = 12 archivos
