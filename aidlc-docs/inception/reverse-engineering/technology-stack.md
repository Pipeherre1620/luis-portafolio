# Stack Tecnológico (Technology Stack)

## Lenguajes de Programación (Programming Languages)
- **TypeScript**: Tipado estático y configuración estricta (`tsconfig.json` con `astro/tsconfigs/strict`).
- **JavaScript (ES Modules)**: Utilizado en `astro.config.mjs` y en scripts de cliente para interactividad liviana.
- **HTML5**: Semántica web nativa (`<nav>`, `<section>`, `<article>`, `<footer>`).
- **CSS3 / Vanilla CSS**: Estilos puros sin preprocesadores pesados, empleando CSS Custom Properties (variables), Media Queries, Flexbox, CSS Grid y efectos de backdrop-filter.

---

## Frameworks y Librerías Principales
- **Astro (v7.2.3)**: Generador de sitios estáticos de última generación centrado en contenido y rendimiento sin JavaScript innecesario.

---

## Infraestructura y Hosting
- **Arquitectura de Despliegue**: Sitio estático compilado a HTML/CSS/JS puros en la carpeta `dist/`.
- **Servicios Cloud Compatibles**: AWS S3 + CloudFront, Vercel, Netlify, Cloudflare Pages o GitHub Pages.
- **Zero-Backend**: Sin necesidad de servidores Node.js dedicados en tiempo de ejecución ni bases de datos activas.

---

## Herramientas de Compilación y Desarrollo (Build Tools)
- **Node.js**: Motor de ejecución en desarrollo (requerido `>= 22.12.0` según `package.json`).
- **npm**: Gestor de dependencias de Node.js.
- **Vite (interno en Astro)**: Servidor de desarrollo con Hot Module Replacement (HMR) y empaquetador de producción.

---

## Tipografía y Recursos Externos
- **Google Fonts CDN**: Familia tipográfica `Inter` (pesos 400, 500, 600) precargada vía `<link rel="preconnect">`.

---

## Herramientas de Calidad y Pruebas (Testing Tools)
- **Comprobación de Tipos**: `astro check` y compilador de TypeScript (`tsc`).
- **Frameworks de Pruebas Automatizadas (Unit/E2E)**: No configurados actualmente en el proyecto.
