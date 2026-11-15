## 🌐 Sobre el Proyecto

Portfolio Dev es mi portafolio profesional, el sitio que estás viendo ahora. Presenta proyectos, experiencias, cursos, tecnologías e idiomas, y todo es trilingüe: el sitio entero, textos y contenido, aparece en portugués, inglés o español a partir de una única fuente de datos.

El contenido no está escrito dentro de los componentes. Vive en la base de datos y se actualiza con scripts, así que cambiar un texto o agregar un proyecto no exige tocar el código de las pantallas.

Sitio en línea: [lloliveira.dev](https://lloliveira.dev)

## 🚀 Visión General de la Arquitectura

- **Renderizado en el servidor primero**: cada página busca y traduce sus datos en el servidor y entrega al navegador solo texto simple.
- **Server Actions como única puerta de datos**: no hay rutas de API, y el acceso a la base de datos nunca llega al navegador.
- **Traducción en tres capas**: textos de la interfaz, contenido de la base de datos y secciones estructuradas del currículum.
- **Contenido versionado en scripts**: cada script lleva los tres idiomas y puede ejecutarse otra vez sin efectos secundarios.

- ✅ Idioma en la ruta (`/pt`, `/en`, `/es`), sin páginas duplicadas
- ✅ Contenido localizado guardado como JSON `{ pt, en, es }` y reducido a texto antes de llegar a la pantalla
- ✅ Tema claro y oscuro, con la misma paleta de colores en ambos
- ✅ Las imágenes y el README de los proyectos vienen de un repositorio de archivos propio

## 🛠️ Principales Recursos

### 🏠 Inicio y Sobre mí
- ✅ Una presentación con las principales tecnologías orbitando la foto
- ✅ Una página Sobre mí contada como un río: el desplazamiento conduce la historia en horizontal
- ✅ Fotos con crédito a sus autores

### 📄 Currículum
- ✅ Pestañas laterales: experiencias, tecnologías, cursos e idiomas
- ✅ Un mapa de la carrera, con la línea subiendo por área de actuación
- ✅ Detalles de cada experiencia en pestañas, con las cifras destacadas
- ✅ Tecnologías con evidencia de uso: desde cuándo, y en qué experiencias, cursos y proyectos

### 🗂️ Proyectos
- ✅ Filtro por categoría
- ✅ Cada proyecto muestra su README en el idioma de quien visita

### ✉️ Contacto
- ✅ Un formulario validado que guarda en la base de datos y envía un correo

## 🧭 Próximos Pasos

- 🔜 Reactivar el asistente de IA, con el límite de uso controlado en el servidor
- 🔜 Rediseñar las demás secciones del currículum (cursos e idiomas)
- 🔜 Fechas e imágenes para todos los proyectos
