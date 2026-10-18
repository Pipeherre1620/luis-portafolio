# Plan de Generación de Código (Code Generation Plan)
## Unidad de Trabajo: Brand Identity & Visual System Enhancement (`brand-identity-visual-system`)

---

## 1. Contexto de la Unidad y Dependencias
- **Unidad**: `brand-identity-visual-system`
- **Tipo de Proyecto**: Brownfield (Astro v7 + TypeScript + Vanilla CSS)
- **Directorio Raíz de Aplicación**: `c:/Repositorios/Personal/luis-portafolio`
- **Requisitos Implementados**:
  - `FR-01`: Componente Isotipo Vectorial de la Gorra `{/}`
  - `FR-02`: Actualización de Marca en Navbar
  - `FR-03`: Actualización de Favicons del Navegador
  - `FR-04`: Firma de Marca en Footer (`Contact.astro`)
  - `FR-05`: Integración Gráfica en Sección Hero (`Hero.astro`)
  - `FR-06`: Normalización del Design System en `global.css`
  - `FR-07`: Refinamiento Estético y Tipado en Componentes Clave (`Experience.astro`, `Projects.astro`)
  - `NFR-01` a `NFR-05`: Rendimiento estático, estética premium, responsividad, accesibilidad WCAG AA y simplicidad (cero backend).
- **Regla Crítica**: El código de la aplicación se genera EXCLUSIVAMENTE en la raíz (`src/`, `public/`). `aidlc-docs/` solo almacena documentación markdown.

---

## 2. Secuencia Detallada de Generación (Single Source of Truth)

### Paso 1: Normalización de Tokens y Estilos en `src/styles/global.css`
- [x] Eliminar bloques y variables duplicadas en `:root`.
- [x] Incorporar la paleta oficial de marca del Universo Herre:
  - `--background`: `#0D1117`
  - `--surface`: `#161B22`
  - `--surface-card`: `#1A222D`
  - `--foreground`: `#F0F6FC`
  - `--muted`: `#8B949E`
  - `--accent`: `#38BDF8` (Cyan Arquitecto)
  - `--accent-hover`: `#0EA5E9`
  - `--accent-glow`: `rgba(56, 189, 248, 0.25)`
  - `--border`: `rgba(240, 246, 252, 0.1)`
  - `--border-hover`: `rgba(56, 189, 248, 0.3)`
- [x] Mantener resets limpios, scroll suave y estilos para la clase `.visible`.
- **Archivo afectado**: `src/styles/global.css` (Modificación in-place)

### Paso 2: Creación del Componente Vectorial `src/components/LogoCap.astro`
- [x] Crear el componente `src/components/LogoCap.astro` con la silueta SVG de la gorra:
  - Domo/corona con degradado sutil (`capGradient`).
  - Visera con curvatura geométrica y ribete inferior.
  - Botón superior.
  - Glifo interior `{/}` centrado en tipografía monospace con resplandor sutil Cyan (`#38BDF8`) y llaves en blanco (`#F0F6FC`).
- [x] Declarar `interface Props` con `size?: number`, `showText?: boolean`, `text?: string`, `class?: string`.
- [x] Soportar modo texto horizontal con tipografía geométrica `PIPEHERRE`.
- **Archivo afectado**: `src/components/LogoCap.astro` (Creación)

### Paso 3: Actualización e Integración en `src/components/Navbar.astro`
- [x] Importar `LogoCap.astro` en `Navbar.astro`.
- [x] Reemplazar el texto plano `<a class="logo" href="/">PIPEHERRE</a>` por una composición que combine el isotipo de la gorra (34px) con el texto de marca.
- [x] Ajustar estilos de navegación para asegurar alineación vertical y hover en color `--accent`.
- [x] Verificar que el menú móvil y el botón hamburguesa funcionen fluidamente.
- **Archivo afectado**: `src/components/Navbar.astro` (Modificación in-place)

### Paso 4: Actualización del Favicon Vectorial en `public/favicon.svg`
- [x] Crear `public/favicon.svg` con la gorra `{/}` contenida en un squircle moderno de fondo `#0D1117` con borde `#161B22` y acento `#38BDF8`.
- [x] Asegurar excelente contraste y nitidez en 16x16 y 32x32 píxeles.
- **Archivo afectado**: `public/favicon.svg` (Modificación in-place)

### Paso 5: Integración Gráfica y Refinamiento en `src/components/Hero.astro`
- [x] Integrar un badge o firma visual con el isotipo de la gorra `{/}` en la tarjeta de perfil personal o en el encabezado de `Hero.astro`.
- [x] Ajustar la rejilla blueprint de fondo y el pill de estado para usar los nuevos tokens de color (`#0D1117`, `#38BDF8`).
- [x] Refinar botones de acción (`.btn-primary` y `.btn-secondary`) con transiciones suaves y microanimaciones de hover.
- **Archivo afectado**: `src/components/Hero.astro` (Modificación in-place)

### Paso 6: Actualización de Marca en Footer en `src/components/Contact.astro`
- [x] Importar `LogoCap.astro` en `Contact.astro`.
- [x] Sustituir la firma de texto simple del footer por un contenedor elegante con el isotipo de la gorra `{/}` y el copyright actualizado: `PIPEHERRE • © 2026 Luis Felipe Herreño`.
- [x] Refinar las tarjetas/enlaces de contacto (Email, LinkedIn, GitHub) con efectos hover sutiles.
- **Archivo afectado**: `src/components/Contact.astro` (Modificación in-place)

### Paso 7: Refinamiento Estético y de Tipado en `Experience.astro` y `Projects.astro`
- [x] Añadir interfaces TypeScript explícitas (`interface ExperienciaItem`, `interface ProyectoItem`) en el frontmatter de cada componente.
- [x] Actualizar los contenedores de tarjetas para usar `--surface`, `--surface-card`, bordes sutiles y tags de tecnologías refinados.
- [x] Verificar consistencia de espaciados y tipografía sin inventar datos ni eliminar contenido existente.
- **Archivos afectados**: `src/components/Experience.astro` y `src/components/Projects.astro` (Modificación in-place)

### Paso 8: Generación de Resumen de Código
- [x] Crear `aidlc-docs/construction/brand-identity-visual-system/code/code-summary.md` detallando las decisiones técnicas implementadas y archivos modificados.
- **Archivo afectado**: `aidlc-docs/construction/brand-identity-visual-system/code/code-summary.md` (Creación)

### Paso 9: Verificación de Calidad y Cero Regresiones
- [x] Verificar que no existan archivos duplicados o copias accidentales.
- [x] Comprobar que no se hayan introducido dependencias externas en `package.json`.
