# Documentación de Interfaces y APIs (API Documentation)

## Enrutamiento y Enlaces (Routing & Navigation Endpoints)
El portafolio opera como una aplicación estática de una sola página (SPA/SSG) con navegación interna por anclas (`#id`):

| Ancla / Ruta | Propósito | Destino / Sección |
| :--- | :--- | :--- |
| `/` | Entrada principal del sitio | Carga `src/pages/index.astro` |
| `#hero` | Sección de inicio | Portada principal y titular profesional |
| `#posts` | Publicaciones | Carrusel de artículos de LinkedIn |
| `#about` | Sobre mí | Descripción de perfil y habilidades |
| `#experience` | Experiencia | Historial laboral y logros profesionales |
| `#projects` | Proyectos | Catálogo de proyectos seleccionados |
| `#architecture` | Arquitectura | Principios de diseño de sistemas |
| `#contact` | Contacto | Canales de comunicación directa |

---

## Interfaces Internas de Componentes (Component Props & Internal APIs)

### `Layout.astro`
- **Props Interface**:
  ```typescript
  interface Props {
      title?: string;       // Título de la pestaña del navegador (Default: "Luis Felipe Herreño | Software Engineer")
      description?: string; // Meta descripción para buscadores (SEO)
  }
  ```
- **Slots**:
  - `<slot />`: Contenido principal de la página (inyectado desde `index.astro`).

### `Navbar.astro`
- **Props**: Ninguna (componente autónomo).
- **Eventos del DOM / APIs de Cliente**:
  - `click` en `.menu-button`: Alterna la clase `.open` en `.mobile-menu` y actualiza atributos de accesibilidad `aria-expanded` y `aria-label`.
  - `click` en `.mobile-menu a`: Cierra el menú móvil al seleccionar cualquier sección.

### `Layout.astro` (Script de Intersección)
- **APIs del Navegador Utilizadas**:
  - `IntersectionObserver`: Detecta cuando los elementos `<section>` alcanzan un umbral del 15% (`threshold: 0.15`) en la ventana gráfica y agrega la clase CSS `.visible`.

---

## Modelos de Datos Internos (Data Models)

### Modelo de Experiencia (`Experience.astro`)
```typescript
interface ExperienciaItem {
    periodo: string;        // Ej: "2024 — PRESENTE"
    cargo: string;          // Ej: "Líder Técnico"
    empresa: string;        // Ej: "Periferia IT"
    contexto: string;       // Ej: "Soluciones financieras · BRE-B"
    descripcion: string;    // Resumen del alcance y rol
    logros: string[];       // Lista de logros concretos alcanzados
    tecnologias: string[];  // Stack tecnológico aplicado (ej: Java, AWS, Spring Boot)
}
```

### Modelo de Proyecto (`Projects.astro`)
```typescript
interface ProyectoItem {
    numero: string;         // Identificador secuencial ("01", "02")
    titulo: string;         // Nombre del proyecto (ej: "PIPEHERRE", "QuickTicket")
    categoria: string;      // Tipo de proyecto (ej: "Portafolio personal", "Laboratorio de arquitectura")
    descripcion: string;    // Explicación técnica y propósito
    tecnologias: string[];  // Herramientas y tecnologías aplicadas
}
```

### Modelo de Principio de Arquitectura (`Architecture.astro`)
```typescript
interface PrincipioItem {
    numero: string;         // Identificador numérico ("01" a "06")
    titulo: string;         // Título del principio (ej: "Sistemas Distribuidos")
    descripcion: string;    // Definición del criterio arquitectónico
}
```
