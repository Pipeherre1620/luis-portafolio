# Instrucciones de Compilación (Build Instructions)

## Prerrequisitos
- **Herramienta de Compilación**: Astro v7.2.3 con motor Vite integrado.
- **Entorno de Ejecución**: Node.js `>= 22.12.0` y npm.
- **Dependencias**: Administradas en `package.json` (`astro: ^7.2.3`).
- **Variables de Entorno**: No requeridas (arquitectura de frontend 100% estática).
- **Requisitos del Sistema**: Compatible con Windows, Linux y macOS.

---

## Pasos de Compilación

### 1. Instalación de Dependencias
Para asegurar que los paquetes y binarios de Astro estén sincronizados:
```bash
npm install
```

### 2. Configuración del Entorno
El proyecto es un sitio web estático Jamstack, por lo que no requiere variables de entorno ni credenciales de base de datos para la compilación estándar.

### 3. Compilar el Proyecto Completo
Para compilar los componentes de Astro, procesar el bundle de estilos CSS globales y generar el sitio estático optimizado en el directorio `dist/`:

En sistemas Windows (PowerShell / CMD):
```bash
cmd /c npm run build
```
O directamente con el binario de Astro:
```bash
npx astro build
```

### 4. Verificar el Éxito de la Compilación
- **Salida esperada en consola**:
  ```text
  [build] output: "static"
  [build] mode: "static"
  [build] directory: ...\dist\
  [build] 1 page(s) built
  [build] Complete!
  ```
- **Artefactos generados**:
  - `dist/index.html`: Página principal minificada con metadata SEO y componentes renderizados.
  - `dist/favicon.svg`: Ícono vectorial squircle con la gorra desarrollador `{/}`.
  - `dist/_astro/`: Hojas de estilo empaquetadas y assets de alto rendimiento.
  - `dist/images/`: Recursos visuales estáticos.

### 5. Previsualización Local
Para verificar la versión de producción en un servidor HTTP local:
```bash
cmd /c npm run preview
```
El servidor servirá la carpeta `dist/` en `http://localhost:4321/` por defecto.

---

## Solución de Problemas Frecuentes (Troubleshooting)

### Error de Política de Ejecución en PowerShell (`PSSecurityException`)
- **Causa**: Las políticas de ejecución restringidas en Windows impiden ejecutar scripts `.ps1` como `npm.ps1`.
- **Solución**: Invocar el comando antecedido por `cmd /c` (`cmd /c npm run build`) o habilitar la ejecución temporalmente mediante `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`.

### Problemas de Caché o Tipados Desactualizados
- **Causa**: Inconsistencia temporal en los metadatos de `.astro/` o en el optimizador de dependencias de Vite.
- **Solución**: Eliminar la carpeta `.astro/` y volver a ejecutar la compilación (`cmd /c npx astro sync && cmd /c npm run build`).
