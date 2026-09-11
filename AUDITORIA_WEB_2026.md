# Auditoría web Garrido Sportech — 2026

## Objetivo

Posicionar Garrido Sportech como una empresa chilena que desarrolla hardware y software para la medición del rendimiento humano, con una experiencia clara para profesionales, universidades y centros deportivos.

## Diagnóstico ejecutivo

La web actual comunica el área general de trabajo y presenta evidencia científica real, pero todavía funciona como una página institucional única. Los productos, el software y las acciones de cotización o descarga necesitan una jerarquía más clara. La identidad visual es coherente con tecnología deportiva, aunque el exceso de efectos, tarjetas y estilos embebidos reduce la percepción de producto técnico premium.

## Clasificación de elementos

### Mantener

- Identidad oscura con acentos turquesa.
- Fotografías reales de productos.
- Contacto directo mediante WhatsApp.
- Publicaciones científicas verificables.
- Descargas públicas mediante GitHub Releases.
- Dominio propio `garridosportech.cl`.

### Mejorar

- Mensaje principal: explicar en segundos qué se diseña, qué se mide y para quién.
- Tipografía, espaciado, jerarquía y consistencia de botones.
- Calidad, recorte, peso y carga diferida de imágenes.
- Accesibilidad del menú, formularios, foco y navegación por teclado.
- Metadatos SEO, Open Graph y URL canónica.
- Presentación del software con capturas, versión, compatibilidad y hardware asociado.
- Estado visual de versión estable, beta y versiones históricas.

### Reorganizar

- Navegación: Inicio, Productos, Software, Tecnología, Investigación, Nosotros y Contacto.
- Productos por líneas: plataformas de fuerza, dinamometría, saltabilidad y accesorios.
- Descargas: última versión visible; historial dentro de un bloque secundario.
- Sectores atendidos como evidencia de aplicaciones, no como eje principal de navegación.
- Publicaciones dentro de una sección más amplia de investigación y validación.

### Eliminar

- Ejecutables almacenados directamente dentro del repositorio web.
- Campos `_subject`, `_captcha` y `_next` duplicados en el formulario.
- Redirecciones del formulario al dominio antiguo de GitHub Pages.
- Animaciones permanentes de botones de descarga.
- Estilos inline repetidos en los botones.
- Mensajes genéricos que no describen capacidades concretas.

### Crear

- Fichas individuales de productos.
- Sección específica de software.
- Comparación clara entre versiones disponibles.
- Sección Hardware + Software con el flujo medición → análisis → exportación.
- CTA consistentes para ver producto, descargar y solicitar cotización.
- README del repositorio web con estructura, publicación y mantenimiento.
- Política simple para publicar versiones y comprobar enlaces.
- Estructura preparada para traducción ES/EN.

## Problemas técnicos prioritarios

1. `index.html` contiene estructura, estilos y comportamiento en un único archivo.
2. Las imágenes principales pesan aproximadamente 1,4–1,5 MB cada una.
3. Dos ejecutables históricos de aproximadamente 170 MB están versionados dentro de `software/`.
4. El formulario tiene controles ocultos duplicados y redirecciones inconsistentes.
5. Open Graph utiliza una ruta relativa y falta URL canónica.
6. Las imágenes de contenido no usan `loading="lazy"`, dimensiones explícitas ni formatos modernos.
7. El menú móvil cambia numerosos estilos directamente desde JavaScript y no expone correctamente su estado accesible.
8. Las descargas mezclan versiones actuales, antiguas y experimentales sin clasificación.

## Arquitectura propuesta

### Navegación principal

- Inicio
- Productos
- Software
- Tecnología
- Investigación
- Nosotros
- Contacto

### Página de inicio

1. Hero: propuesta de valor y producto real.
2. Líneas de producto.
3. Qué medimos.
4. Integración hardware + software.
5. Software destacado.
6. Evidencia científica.
7. Aplicaciones profesionales.
8. CTA de cotización.

### Productos

- Plataformas de fuerza.
- Dinamometría y celdas de carga.
- Saltabilidad y plataformas de contacto.
- Accesorios y soportes.

Cada ficha debe incluir solamente información confirmada: uso, variables, compatibilidad, software asociado, imágenes y CTA.

### Software

- G-FORCE RFD Analyzer.
- GARRIDO JumpAnalyzer.
- G-Jump.

Cada producto debe mostrar descripción, captura, hardware compatible, sistema operativo, versión actual, estado de la versión y descarga.

## Arquitectura de GitHub propuesta

- Repositorio web público: código del sitio, imágenes optimizadas y documentación.
- Repositorios de software: código fuente con visibilidad definida por el propietario.
- Repositorio web Releases: ejecutables públicos descargables.
- Convención de etiquetas: `producto-vX.Y` y `producto-vX.Y-beta`.
- Una release debe incluir título, fecha, cambios principales, compatibilidad, archivo, tamaño y SHA-256.
- La web debe enlazar únicamente releases públicas y comprobar el código HTTP antes de publicarse.

## Información pendiente de confirmar

- Lista definitiva de modelos actualmente comercializados.
- Especificaciones verificadas de cada producto.
- Compatibilidad exacta entre hardware y software.
- Sistemas operativos admitidos por cada versión.
- Fotografías oficiales que deben utilizarse por modelo.
- Correo comercial definitivo del formulario.
- Condiciones de soporte, garantía y actualizaciones.
- Contenido y disponibilidad futura en inglés.

## Orden de implementación

1. Normalizar GitHub, releases y documentación.
2. Definir design system.
3. Rediseñar la portada en rama independiente.
4. Crear productos y software.
5. Optimizar imágenes y experiencia móvil.
6. Validar enlaces, formulario, accesibilidad y rendimiento.
7. Revisar visualmente con el propietario.
8. Integrar en `main` y desplegar.
