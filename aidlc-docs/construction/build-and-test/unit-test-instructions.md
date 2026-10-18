# Instrucciones de Pruebas Unitarias (Unit Test Instructions)

## Propósito
Verificar la integridad estática, contratos de tipado TypeScript y propiedades de renderizado de cada componente UI de Astro en aislamiento sin dependencias externas pesadas.

---

## 1. Validación de Contratos e Interfaces de Datos

### Componentes y Contratos Evaluados
1. **`LogoCap.astro`**:
   - `Props`: `size?: number` (default: 32), `showText?: boolean` (default: true), `className?: string` (default: `""`).
   - Símbolo interno: `{/}` vectorial centrado con glow `#38BDF8`.
   - Renderizado condicional del texto de marca `PIPEHERRE`.
2. **`Experience.astro`**:
   - Interfaz `ExperienciaItem`: Valida que cada elemento posea `puesto: string`, `empresa: string`, `periodo: string`, `descripcion: string`, y `tecnologias: string[]`.
3. **`Projects.astro`**:
   - Interfaz `ProyectoItem`: Valida que cada elemento posea `titulo: string`, `descripcion: string`, `tags: string[]`, y enlaces opcionales `link?: string` y `github?: string`.

---

## 2. Ejecución de Pruebas de Diagnóstico Unitario

### Ejecución de Validación de Tipos y Compilación de Módulos
El compilador nativo de Astro analiza sintácticamente y evalúa el frontmatter TypeScript de cada componente individualmente:

```bash
cmd /c npm run build
```

### Criterios de Aceptación Unitarios
- **Cero errores de compilación**: Todos los bloques `<script>` y frontmatter `---` deben compilar sin advertencias de sintaxis.
- **Tipado estricto**: Las colecciones de experiencia y proyectos cumplen con las estructuras `ExperienciaItem[]` y `ProyectoItem[]`.
- **Integridad de Props**: `LogoCap.astro` acepta propiedades opcionales sin provocar fallos de renderizado cuando no se proveen argumentos.

---

## 3. Revisión de Resultados
- **Resultado Esperado**: `1 page(s) built in X.XXs - Complete!` con 0 errores de tipado o parsing.
- **En caso de fallo**:
  1. Revisar la traza de Astro en la consola para ubicar el archivo y línea específica.
  2. Verificar que los tipos coincidan con las interfaces definidas.
  3. Re-ejecutar la compilación para validar la resolución.
