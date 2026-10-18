# Plan de Ejecución (Execution Plan)

## Resumen del Análisis Detallado (Detailed Analysis Summary)

### Alcance de Transformación (Brownfield Project)
- **Tipo de Transformación**: Refactorización estética de interfaz, consolidación del sistema de diseño (Design Tokens) e integración de la identidad de marca matriz (gorra de programador con glifo `{/}`).
- **Cambios Principales**:
  - Creación del componente reutilizable `LogoCap.astro` con renderizado SVG vectorial exacto de la gorra y glifo `{/}`.
  - Integración del isotipo en `Navbar.astro`, `Contact.astro` (footer) y como badge de autoría técnica en `Hero.astro`.
  - Reemplazo y modernización de `public/favicon.svg` con la silueta de la gorra adaptada a 32x32 / squircle.
  - Depuración y consolidación de `src/styles/global.css`: eliminación de variables duplicadas y estandarización de la paleta oficial (fondo `#0D1117`, superficie `#161B22`, texto `#F0F6FC`, acento Cyan Arquitecto `#38BDF8`).
  - Refinamiento de contraste, espaciados y tipografía en componentes clave (`Hero.astro`, `Experience.astro`, `Projects.astro`).
- **Componentes Afectados**:
  - `src/components/Navbar.astro`
  - `src/components/Hero.astro`
  - `src/components/Contact.astro`
  - `src/components/Experience.astro`
  - `src/components/Projects.astro`
  - `src/styles/global.css`
  - `public/favicon.svg`
  - `src/components/LogoCap.astro` (nuevo)

### Evaluación de Impacto de Cambios
- **Cambios Visibles al Usuario**: Sí. Identidad visual consistente, logotipo distintivo, paleta cromática sofisticada y mejor legibilidad en dispositivos móviles.
- **Cambios Estructurales de Arquitectura**: No. Se mantiene estrictamente el modelo SSG (Static Site Generation) con Astro v7 sin backend ni infraestructura adicional.
- **Cambios en Modelos de Datos / Base de Datos**: No. No existen bases de datos activas.
- **Cambios en APIs / Contratos Externos**: No. Se preservan todos los enlaces profesionales existentes (LinkedIn, GitHub, correo).
- **Impacto en Requisitos No Funcionales (NFR)**: Altamente positivo. Mejor accesibilidad (WCAG AA), mayor contraste, reducción de CSS redundante y rendimiento web óptimo.

### Relaciones entre Componentes y Grafo de Dependencias
```mermaid
graph TD
    GlobalCSS["src/styles/global.css (Tokens de Diseño)"]
    LogoCap["src/components/LogoCap.astro (Isotipo Vectorial)"]
    Favicon["public/favicon.svg (Favicon del Navegador)"]
    
    Navbar["src/components/Navbar.astro"]
    Hero["src/components/Hero.astro"]
    Contact["src/components/Contact.astro"]
    Experience["src/components/Experience.astro"]
    Projects["src/components/Projects.astro"]

    GlobalCSS --> Navbar
    GlobalCSS --> Hero
    GlobalCSS --> Contact
    GlobalCSS --> Experience
    GlobalCSS --> Projects
    
    LogoCap --> Navbar
    LogoCap --> Hero
    LogoCap --> Contact
```

### Evaluación de Riesgo (Risk Assessment)
- **Nivel de Riesgo**: **Bajo (Low)**. Modificaciones puramente estéticas y de marcado en frontend estático sin impacto en lógica de servidor ni dependencias externas.
- **Complejidad de Reversión (Rollback)**: **Sencilla (Easy)**. Todos los cambios están bajo control de versiones Git en un repositorio local.
- **Complejidad de Pruebas**: **Sencilla (Simple)**. Comprobación directa mediante servidor local de desarrollo (`astro dev`), compilación estática (`astro build`) e inspección visual y semántica.

---

## Visualización del Flujo de Trabajo (Workflow Visualization)

```mermaid
flowchart TD
    Start(["Solicitud del Usuario"])
    
    subgraph INCEPTION["🔵 FASE DE INCEPCIÓN"]
        WD["Detección del Espacio de Trabajo<br/><b>COMPLETADO</b>"]
        RE["Ingeniería Inversa<br/><b>COMPLETADO</b>"]
        RA["Análisis de Requisitos<br/><b>COMPLETADO</b>"]
        US["Historias de Usuario<br/><b>OMITIDO</b>"]
        WP["Planificación del Flujo de Trabajo<br/><b>EN PROGRESO</b>"]
        AD["Diseño de la Aplicación<br/><b>OMITIDO</b>"]
        UG["Generación de Unidades<br/><b>OMITIDO</b>"]
    end
    
    subgraph CONSTRUCTION["🟢 FASE DE CONSTRUCCIÓN"]
        FD["Diseño Funcional<br/><b>OMITIDO</b>"]
        NFRA["Requisitos NFR<br/><b>OMITIDO</b>"]
        NFRD["Diseño NFR<br/><b>OMITIDO</b>"]
        ID["Diseño de Infraestructura<br/><b>OMITIDO</b>"]
        CP["Planificación de Código<br/><b>EJECUTAR</b>"]
        CG["Generación de Código<br/><b>EJECUTAR</b>"]
        BT["Compilación y Pruebas<br/><b>EJECUTAR</b>"]
    end
    
    subgraph OPERATIONS["🟡 FASE DE OPERACIONES"]
        OPS["Operaciones<br/><b>RESERVADO</b>"]
    end
    
    Start --> WD
    WD --> RE
    RE --> RA
    RA --> WP
    WP --> CP
    CP --> CG
    CG --> BT
    BT --> End(["Finalizado"])
    
    style WD fill:#4CAF50,stroke:#1B5E20,stroke-width:3px,color:#fff
    style RE fill:#4CAF50,stroke:#1B5E20,stroke-width:3px,color:#fff
    style RA fill:#4CAF50,stroke:#1B5E20,stroke-width:3px,color:#fff
    style WP fill:#4CAF50,stroke:#1B5E20,stroke-width:3px,color:#fff
    style CP fill:#FFA726,stroke:#E65100,stroke-width:3px,stroke-dasharray: 5 5,color:#000
    style CG fill:#FFA726,stroke:#E65100,stroke-width:3px,stroke-dasharray: 5 5,color:#000
    style BT fill:#FFA726,stroke:#E65100,stroke-width:3px,stroke-dasharray: 5 5,color:#000
    style US fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style AD fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style UG fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style FD fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style NFRA fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style NFRD fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style ID fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style OPS fill:#BDBDBD,stroke:#424242,stroke-width:2px,stroke-dasharray: 5 5,color:#000
    style Start fill:#CE93D8,stroke:#6A1B9A,stroke-width:3px,color:#000
    style End fill:#CE93D8,stroke:#6A1B9A,stroke-width:3px,color:#000
    style INCEPTION fill:#BBDEFB,stroke:#1565C0,stroke-width:3px,color:#000
    style CONSTRUCTION fill:#C8E6C9,stroke:#2E7D32,stroke-width:3px,color:#000
    style OPERATIONS fill:#FFF59D,stroke:#F57F17,stroke-width:3px,color:#000

    linkStyle default stroke:#333,stroke-width:2px
```

### Alternativa Textual del Flujo de Trabajo
- **Fase de Incepción**:
  1. Detección del Espacio de Trabajo: COMPLETADO.
  2. Ingeniería Inversa: COMPLETADO.
  3. Análisis de Requisitos: COMPLETADO.
  4. Historias de Usuario: OMITIDO (no requerido para portafolio personal individual con requerimientos ya cerrados).
  5. Planificación del Flujo de Trabajo: EN PROGRESO.
  6. Diseño de la Aplicación: OMITIDO (cambios dentro de límites de componentes frontend existentes; no hay capa de servicios).
  7. Generación de Unidades de Trabajo: OMITIDO (se trata de una única unidad de trabajo cohesionada de UI/UX).
- **Fase de Construcción (Unidad Única: Identidad de Marca y Refactorización Estética)**:
  1. Diseño Funcional: OMITIDO (no hay lógica de negocio compleja ni esquemas de datos).
  2. Requisitos NFR: OMITIDO (cubiertos en requisitos; reglas de seguridad omitidas a solicitud).
  3. Diseño NFR: OMITIDO (no hay cambios en infraestructura).
  4. Diseño de Infraestructura: OMITIDO (sitio estático en Astro sin cambios de alojamiento).
  5. Planificación de Código (Code Planning): EJECUTAR (creación de plan detallado de implementación por pasos con checkboxes).
  6. Generación de Código (Code Generation): EJECUTAR (implementación de componentes, SVG, estilos y favicons).
  7. Compilación y Pruebas (Build and Test): EJECUTAR (validación con `astro build`, pruebas de renderizado y verificación sin errores).
- **Fase de Operaciones**:
  1. Operaciones: RESERVADO para futuras integraciones de despliegue continuo.

---

## Justificación Detallada de Etapas Omitidas y Ejecutadas

### 🔵 FASE DE INCEPCIÓN
- **Historias de Usuario (SKIP)**: La solicitud es directa y proviene del único usuario y propietario del portafolio. Los requisitos funcionales y criterios de aceptación ya están formalizados en `requirements.md` y `Contexto_mejoras.md`.
- **Diseño de la Aplicación (SKIP)**: No se crearán microservicios, APIs de backend ni capas de servicios complejas; la arquitectura sigue siendo puramente frontend con componentes Astro autosuficientes.
- **Generación de Unidades (SKIP)**: Todo el trabajo constituye una única unidad de trabajo indivisible ("Evolución de Identidad de Marca y Sistema Visual del Portafolio").

### 🟢 FASE DE CONSTRUCCIÓN
- **Diseño Funcional (SKIP)**: No hay algoritmos de negocio complejos ni mutaciones de estado de datos persistentes.
- **Evaluación y Diseño NFR (SKIP)**: No se requieren patrones arquitectónicos nuevos de infraestructura; la extensión de seguridad fue explícitamente omitida por el usuario.
- **Diseño de Infraestructura (SKIP)**: La arquitectura permanece como un sitio estático compatible con cualquier proveedor de hosting estático (GitHub Pages, S3/CloudFront, Cloudflare Pages, etc.).
- **Planificación de Código (EXECUTE)**: Obligatoria por AI-DLC para estructurar paso a paso la generación de código y garantizar trazabilidad mediante checkboxes.
- **Generación de Código (EXECUTE)**: Creación de `LogoCap.astro`, actualización de `Navbar.astro`, `Hero.astro`, `Contact.astro`, `favicon.svg`, `global.css`, `Experience.astro`, `Projects.astro`.
- **Compilación y Pruebas (EXECUTE)**: Verificación exhaustiva de build con `astro build` y comprobación en navegador para garantizar cero regresiones y máxima fidelidad visual.

---

## Criterios de Éxito
1. Integración impecable de la gorra con `{/}` en Navbar, Favicon, Footer y Hero.
2. Normalización de `global.css` eliminando variables duplicadas y aplicando la paleta oficial con acento `#38BDF8`.
3. Compilación limpia y exitosa de `astro build` sin advertencias críticas ni errores.
4. Cero dependencias adicionales añadidas en `package.json`.
5. Experiencia responsive y de contraste visual superior.
