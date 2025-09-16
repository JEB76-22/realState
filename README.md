## Real State – Sitio web inmobiliario estático

**Resumen**: Proyecto front-end que implementa un sitio inmobiliario responsive con **SASS/SCSS**, metodología **BEM**, **CSS Grid/Flexbox** y un pipeline de build con **Gulp**. Incluye optimización automática de imágenes (JPEG/PNG → **WebP**/**AVIF**), generación de **sourcemaps**, **autoprefixing** y minificación CSS para un rendimiento óptimo en producción.

## 🌐 Demo en Vivo

**Visita el sitio web:** [realState](https://realstate-2025.netlify.app/)

## 📸 Capturas de Pantalla

![Vista Principal](build/img/realState.png)
![Vista Principal](build/img/realState2.png)
![Vista Principal](build/img/realState3.png)
![Vista Principal](build/img/realState4.png)
![Vista Móvil](build/img/realState5.png)
![Vista Móvil](build/img/realState6.png)


### Características principales
- **UI responsive**: Layout fluido con CSS Grid y Flexbox.
- **Arquitectura CSS con BEM**: Nomenclatura predecible y escalable.
- **SASS modular**: Variables, mixins y archivos parciales organizados.
- **Rendimiento**:
  - Minificación CSS y autoprefixer con PostCSS.
  - Optimización de imágenes (imagemin) y generación de WebP/AVIF.
  - Sourcemaps para DX sin sacrificar producción.
- **DX con Gulp 4**: Tareas encadenadas y `watch` para desarrollo en caliente de estilos e imágenes.

### Tecnologías y librerías
- **Lenguajes/estándares**: HTML5, CSS3 (SASS/SCSS), JavaScript (vanilla para interacción puntual).
- **Build**: Gulp 4, PostCSS, Autoprefixer, CSSNano, Sourcemaps.
- **Imágenes**: gulp-imagemin, gulp-webp, gulp-avif.
- **Metodología**: BEM para componentes y utilidades.

### Estructura del proyecto
```text
build/            # Salida de assets optimizados (CSS, imágenes)
  css/
  img/
src/              # Código fuente
  scss/           # SASS modular (base/, ui/, variables, mixins)
  img/            # Imágenes fuente (JPG/PNG/SVG)
index.html        # Landing principal
gulpfile.js       # Tareas de build y watch
package.json      # Scripts y dependencias
```

### Scripts y tareas
- **Desarrollo**:
  - `npm run dev` → Ejecuta `gulp` por defecto: optimiza imágenes (JPG/PNG → WebP/AVIF), compila SASS con sourcemaps, minifica CSS y queda en `watch` sobre `src/scss` e `src/img`.
- **Tareas Gulp individuales** (desde `gulpfile.js`):
  - `gulp css` → Compila SASS, autoprefix, minifica y genera sourcemaps en `build/css`.
  - `gulp imagenes` → Optimiza imágenes originales a `build/img`.
  - `gulp versionWebp` → Genera `.webp` de `src/img/**/*.{png,jpg}` con calidad 50.
  - `gulp versionAvif` → Genera `.avif` de `src/img/**/*.{png,jpg}` con calidad 50.

### Requisitos
- Node.js 14+ y npm

### Instalación
```bash
npm install
npm run dev
```
Abrir `index.html` en el navegador o servir la carpeta del proyecto con tu servidor estático favorito.

### Rendimiento y mejores prácticas
- **CSS**: salida minificada y con autoprefixer para compatibilidad cross-browser (según `browserslist`).
- **Imágenes**: se publican versiones optimizadas (JPEG/PNG) y modernas (WebP/AVIF) para reducir el peso y mejorar LCP/CLS.
- **Caché**: recomienda configurar cache estático a nivel de servidor/CDN y `immutable` para `build/img` y `build/css`.
- **Accesibilidad y SEO**: uso de imágenes responsivas y etiquetas semánticas en `index.html`. Revisar `alt` en imágenes y jerarquía de encabezados.

### Convenciones de código
- **BEM**: `bloque__elemento--modificador` para estilos predecibles y reutilizables.
- **SASS**: centralizar tokens en `src/scss/base/_variables.scss` y utilidades en `src/scss/base/_mixins.scss`.

### Roadmap sugerido
- Añadir servidor de desarrollo local con live-reload.
- Integrar `eslint/stylelint` y `prettier`.
- Generar HTMLs adicionales (listado/detalle de propiedades) o templating estático.

### Autor
**JEB$DEV (Javier Berchtold)**  
GitHub: https://github.com/JEB76-22?tab=repositories
**Correo:** j.e.b.inter@gmail.com

### Licencia
Este proyecto se distribuye bajo la licencia **ISC** (ver `package.json`).
