# Guía de Operaciones y Despliegue (Operations Guide)

## Propósito
Proveer las directrices de despliegue, entrega continua (CI/CD), observabilidad y mantenimiento del portafolio estático de Luis Felipe Herreño (Pipe Herre) tras la culminación de la fase de construcción.

---

## 1. Opciones de Despliegue en Producción (Static Hosting)

Al ser una aplicación de arquitectura JAMstack generada como bundle HTML/CSS/SVG estático en la carpeta `dist/`, el portafolio puede desplegarse en plataformas globales de Edge Hosting con cero coste de infraestructura:

### Opción A: GitHub Pages (Recomendado para repositorios personales)
1. En el repositorio de GitHub, navegar a **Settings** > **Pages**.
2. En **Build and deployment** > **Source**, seleccionar **GitHub Actions**.
3. Utilizar el flujo de trabajo estándar de Astro para GitHub Pages (`.github/workflows/deploy.yml`):
   ```yaml
   name: Deploy to GitHub Pages
   on:
     push:
       branches: [ main ]
     workflow_dispatch:
   permissions:
     contents: read
     pages: write
     id-token: write
   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v4
         - name: Setup Node
           uses: actions/setup-node@v4
           with:
             node-version: 22
         - name: Install dependencies
           run: npm ci
         - name: Build site
           run: npm run build
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v3
           with:
             path: ./dist
     deploy:
       needs: build
       runs-on: ubuntu-latest
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       steps:
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v4
   ```

### Opción B: Cloudflare Pages / Vercel / Netlify
- **Directorio de salida (Build output directory)**: `dist`
- **Comando de compilación (Build command)**: `npm run build`
- **Versión de Node.js**: `22.x`

---

## 2. Monitoreo y Mantenimiento

### Disponibilidad y Chequeo de Salud (Uptime)
- Dado que el sitio es puramente estático servido desde CDN/Edge, el SLA de disponibilidad depende del proveedor de CDN (típicamente > 99.99%).
- Se pueden configurar monitores gratuitos de ping HTTP (como UptimeRobot o BetterStack) apuntando a la URL del dominio con intervalo de verificación de 5 minutos.

### Analítica de Tráfico y Privacidad
- Si se requiere analítica web en el futuro, se recomienda integrar soluciones ligeras y respetuosas de la privacidad sin cookies como:
  - Cloudflare Web Analytics (gratuito y sin scripts invasivos).
  - Umami o Plausible Analytics.

### Procedimiento de Actualización de Contenido
- Para añadir nuevos proyectos o actualizar la experiencia laboral:
  1. Modificar la lista `experiencias` en `src/components/Experience.astro`.
  2. Modificar la lista `proyectos` en `src/components/Projects.astro`.
  3. Ejecutar localmente `cmd /c npm run build` para validar que los tipados TypeScript y el renderizado estático compilen con éxito.
  4. Realizar `git commit` y `git push` a la rama principal para disparo automático del pipeline de despliegue.

---

## 3. Estado del Ciclo de Vida AI-DLC
Con la formalización de las directrices operativas y de despliegue, el ciclo completo del framework adaptativo AI-DLC (Inception, Construction, Operations) se encuentra **concluido al 100%**.
