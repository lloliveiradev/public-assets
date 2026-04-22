## 📚 Acerca del Proyecto

Este proyecto es una propuesta de rediseño para el sitio web de la **SETEC (Serviços Técnicos Gerais)**, un organismo autónomo municipal de la ciudad de Campinas, São Paulo. El objetivo es ofrecer una interfaz moderna, intuitiva y accesible para que los ciudadanos puedan acceder a la información y los servicios públicos de forma eficiente.

El proyecto consiste en un sitio web estático moderno integrado en el ecosistema Firebase, centrado en proporcionar información detallada sobre servicios funerarios, transparencia pública, gestión de publicidad en áreas públicas y acceso a documentos oficiales.

## 🛠️ Stack Tecnológico

### Frontend
- [HTML5](https://html.spec.whatwg.org/) y [CSS3](https://www.w3.org/Style/CSS/) — Estructura y estilos base
- [Bootstrap 5](https://getbootstrap.com/) — Framework CSS para desarrollo responsivo
- [jQuery](https://jquery.com/) — Biblioteca JavaScript para manipulación del DOM
- [FontAwesome](https://fontawesome.com/) — Conjunto de iconos
- [Google Fonts (Roboto)](https://fonts.google.com/specimen/Roboto) — Tipografía

### Backend e Infraestructura
- [Firebase Hosting](https://firebase.google.com/docs/hosting) — Alojamiento rápido y seguro
- [Firebase Firestore](https://firebase.google.com/docs/firestore) — Base de datos NoSQL en tiempo real
- [Firebase Storage](https://firebase.google.com/docs/storage) — Almacenamiento de archivos y documentos
- [Firebase Auth](https://firebase.google.com/docs/auth) — Sistema de autenticación de usuarios

## 🗂️ Estructura del Proyecto

```bash
setec-site/
├── public/                # Contenido principal del sitio
│   ├── assets/            # Recursos estáticos
│   │   ├── css/           # Hojas de estilo
│   │   ├── docs/          # Documentos oficiales y formularios PDF
│   │   ├── fonts/         # Fuentes locales
│   │   ├── images/        # Imágenes y logotipos
│   │   └── svg/           # Vectores e iconos SVG
│   ├── pag/               # Subpáginas temáticas
│   │   ├── funeraria.html     # Servicios funerarios y cementerios
│   │   ├── transparencia.html # Portal de transparencia
│   │   ├── publicidade.html   # Publicidad en áreas públicas
│   │   ├── solo.html          # Gestión del uso del suelo
│   │   └── covid19.html       # Información y protocolos específicos
│   ├── vendor/            # Bibliotecas de terceros
│   └── index.html         # Página de inicio
├── firebase.json          # Configuraciones de Firebase
├── firestore.rules        # Reglas de seguridad de la base de datos
├── storage.rules          # Reglas de seguridad del almacenamiento
└── README.md              # Documentación del proyecto
```

## ✨ Funciones Principales

- **Servicios Funerarios** — Información sobre cementerios, crematorios y planes
- **Transparencia Pública** — Acceso a datos del organismo y rendición de cuentas
- **Documentación en Línea** — Repositorio de formularios y solicitudes (exhumación, traslado, etc.)
- **Gestión de Publicidad** — Licencia de anuncios en áreas públicas y privadas
- **Interfaz Responsiva** — Diseño adaptable para cualquier dispositivo

## 🚀 Cómo Empezar

### Requisitos previos
- Cuenta en [Firebase](https://console.firebase.google.com/)
- [Firebase CLI](https://firebase.google.com/docs/cli) instalado globalmente

### Instalación y Despliegue

1. Clona el repositorio:
```bash
git clone [REPOSITORY_URL]
cd setec-site
```

2. Inicia sesión en Firebase y previsualiza localmente:
```bash
firebase login
firebase serve
```

3. Realiza el despliegue:
```bash
firebase deploy
```

## 📄 Licencia

Este proyecto se desarrolla con el fin de modernizar los servicios públicos de SETEC Campinas y está licenciado bajo la [Licencia MIT](LICENSE).
