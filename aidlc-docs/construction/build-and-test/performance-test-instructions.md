# Instrucciones de Pruebas de Rendimiento (Performance Test Instructions)

## Propósito
Garantizar que la experiencia de usuario y las métricas Core Web Vitals del portafolio cumplan con estándares de excelencia técnica para sitios web estáticos de alto desempeño.

---

## 1. Métricas Objetivas (Core Web Vitals)
- **First Contentful Paint (FCP)**: `< 0.8s`
- **Largest Contentful Paint (LCP)**: `< 1.2s`
- **Cumulative Layout Shift (CLS)**: `0.00` (sin saltos de contenido)
- **Interaction to Next Paint (INP)**: `< 50ms`
- **Peso total del bundle HTML**: `< 50 KB` sin compresión (~8 KB gzipped)
- **Peso de assets vectoriales (SVG)**: `< 5 KB` total

---

## 2. Procedimiento de Medición con Google Lighthouse

### Preparación del Entorno
1. Iniciar la previsualización del build estático de producción:
   ```bash
   cmd /c npm run preview
   ```
2. Abrir Google Chrome en modo incógnito (para evitar interferencias de extensiones).
3. Navegar a `http://localhost:4321/`.

### Ejecución de la Auditoría
1. Abrir Chrome DevTools (`F12` o `Ctrl + Shift + I`).
2. Dirigirse a la pestaña **Lighthouse**.
3. Seleccionar las categorías:
   - [x] Rendimiento (Performance)
   - [x] Accesibilidad (Accessibility)
   - [x] Mejores Prácticas (Best Practices)
   - [x] SEO
4. Dispositivo: Probar tanto en **Mobile** como en **Desktop**.
5. Hacer clic en **Analizar carga de página**.

---

## 3. Criterios de Aceptación y Diagnóstico

| Categoría | Puntuación Mínima Requerida | Estado Estimado |
|---|---|---|
| **Performance** | `≥ 95` | ✅ Óptimo (HTML puro sin scripts bloqueantes) |
| **Accessibility** | `≥ 95` | ✅ Contraste AA verificado, etiquetas semánticas |
| **Best Practices** | `≥ 95` | ✅ HTTPS ready, DOCTYPE y meta viewport |
| **SEO** | `≥ 95` | ✅ Title único, meta description, favicon SVG |

---

## 4. Guía de Optimización en caso de Desviaciones
- Si el LCP aumenta: Verificar compresión de imágenes estáticas en `public/images/`.
- Si el CLS es superior a 0: Asegurar dimensiones fijas de `width` y `height` en elementos multimedia y SVGs.
- Si la accesibilidad disminuye: Verificar relación de contraste en badges y tags de texto secundario.
