# Instrucciones de Pruebas de Integración (Integration Test Instructions)

## Propósito
Verificar la integración correcta y armónica entre el Layout central (`Layout.astro`), los estilos globales (`global.css`), el favicon (`favicon.svg`) y los componentes de sección (`Navbar`, `Hero`, `Experience`, `Projects`, `Contact`).

---

## Escenarios de Prueba de Integración

### Escenario 1: Inyección y Propagación del Sistema de Diseño (`global.css` → Componentes)
- **Descripción**: Comprobar que las variables CSS definidas en `:root` (`--bg-primary: #0D1117`, `--accent-primary: #38BDF8`, `--font-mono`, etc.) se aplican uniformemente en todos los componentes hijos.
- **Verificación**:
  - `Navbar.astro`: Aplica glassmorphism (`--bg-surface-glass`) y borde sutil (`--border-subtle`).
  - `Hero.astro`: Insignia de estado y tarjeta glass con borde cian y fondo degradado.
  - `Experience.astro` y `Projects.astro`: Etiquetas de tecnologías usan tipografía mono y contraste AA.
- **Resultado Esperado**: Ausencia de estilos rotos, tipografías por defecto del navegador o colores no tokenizados.

### Escenario 2: Consistencia del Emblema de Marca (`LogoCap` en Navbar, Hero, Footer y Favicon)
- **Descripción**: Verificar que el símbolo de la gorra con `{/}` esté presente y alineado en los cuatro puntos de contacto principales.
- **Puntos de Verificación**:
  1. **Favicon del navegador**: `<link rel="icon" type="image/svg+xml" href="/favicon.svg" />` en `Layout.astro`.
  2. **Navbar**: Componente `LogoCap` con texto `PIPEHERRE`.
  3. **Hero**: Componente `LogoCap` integrado en la tarjeta de presentación con glow cian.
  4. **Footer (Contact)**: Componente `LogoCap` con copyright y metadata del portafolio.
- **Resultado Esperado**: El símbolo dentro de la gorra es estrictamente `{/}` (código de software/creador), diferenciándose explícitamente de Herrefinance (`{$}`).

### Escenario 3: Navegación de Anclas e Interactividad UI
- **Descripción**: Validar el comportamiento del menú de navegación y los enlaces internos.
- **Pasos**:
  1. Iniciar el servidor local de vista previa: `cmd /c npm run preview`.
  2. Abrir `http://localhost:4321` en el navegador.
  3. Hacer clic en los enlaces de la barra de navegación:
     - `Experiencia` desplaza suavemente a `#experiencia`.
     - `Proyectos` desplaza suavemente a `#proyectos`.
     - `Contacto` desplaza suavemente a `#contacto`.
  4. Probar enlaces externos a LinkedIn, GitHub y correo electrónico (`mailto:`).
- **Resultado Esperado**: `scroll-behavior: smooth` activo; todas las anclas corresponden a identificadores `id` válidos en el DOM.

---

## Ejecución del Entorno de Integración

```bash
# 1. Compilar el bundle estático
cmd /c npm run build

# 2. Servir el bundle localmente
cmd /c npm run preview
```
