<div align="center">
  <div align="center" style="background-color: #fff; padding-top: 10px; padding-bottom: 5px">
    <img src="./full_logo.png" alt="Kairos Logo" width="150"/>
  </div>

  [![Go Lang](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://go.dev)
  [![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactnative.dev)
  [![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
  [![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
  [![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)](https://expo.dev)

</div>

⸻
📋 Índice

- Acerca del Proyecto
- Arquitectura
- Funcionalidades
- Stack Tecnológico
- Estructura del Proyecto
- Requisitos Previos
- Instalación
- Configuración
- Ejecución del Proyecto
- Capturas de Pantalla
- Documentación
- Hoja de Ruta
- Contribución
- Licencia
⸻
📖 Acerca del Proyecto

Kairos es una solución integral de gestión financiera personal que permite a los usuarios controlar sus finanzas de forma inteligente e intuitiva. El proyecto está compuesto por:

- 📱 Aplicación Móvil Multiplataforma (iOS, Android, Web) - React Native + Expo
- 🚀 API REST Backend - Go + Firebase + Cloud Firestore
- 🔐 Sistema de Autenticación Seguro - Firebase Authentication
- 📊 Panel de Análisis Financiero - Gráficos e informes interactivos

¿Por qué Kairos?

En la mitología griega, Kairos representa el momento oportuno, la oportunidad perfecta. Al igual que el concepto mitológico, nuestra aplicación te ayuda a tomar decisiones financieras en el momento adecuado, con la información correcta.
⸻
🏗️ Arquitectura

El proyecto sigue una arquitectura de microservicios con una clara separación entre frontend y backend:

┌─────────────────────────────────────────────────────────────┐
│                     Aplicaciones Móviles (iOS/Android/Web)  │
│              React Native + Expo + TypeScript               │
└───────────────────────┬─────────────────────────────────────┘
                        │ REST API
                        │ (HTTP/JSON)
┌───────────────────────▼─────────────────────────────────────┐
│                    API Backend (Go)                         │
│          Chi Router + Firebase Admin SDK                    │
└───────────────────────┬─────────────────────────────────────┘
                        │
        ┌───────────────┴────────────────┐
        │                                │
┌───────▼────────┐            ┌──────────▼──────────┐
│   Firebase     │            │   Cloud Firestore   │
│ Authentication │            │   (Base de datos NoSQL) │
└────────────────┘            └─────────────────────┘


Principios Arquitectónicos

- ✅ Clean Architecture en el backend (Go)
- ✅ Basado en Componentes en el frontend (React Native)
- ✅ API RESTful para la comunicación
- ✅ Enrutamiento basado en archivos con Expo Router
- ✅ Seguridad de Tipos con TypeScript y Go
- ✅ Inyección de Dependencias e Inversión de Control
- ✅ Patrón Repository para la abstracción de datos
⸻
✨ Funcionalidades

🔐 Autenticación y Seguridad
- ✅ Inicio de sesión con correo y contraseña
- ✅ Inicio de sesión social (Google, Apple)
- ✅ Recuperación de contraseña
- ✅ Autenticación JWT con Firebase
- ✅ Persistencia de sesión
- ✅ Middleware de autorización

💰 Gestión de Transacciones
- ✅ Registro de ingresos y gastos
- ✅ Categorización personalizable
- ✅ Filtros avanzados (periodo, categoría, cuenta)
- ✅ Búsqueda y ordenación
- ✅ Edición y eliminación de transacciones
- ✅ Historial completo

🏦 Cuentas Bancarias
- ✅ Múltiples cuentas (corriente, ahorros, inversión)
- ✅ Soporte para los principales bancos brasileños
- ✅ Saldo en tiempo real
- ✅ Transferencias entre cuentas
- ✅ Categorías personalizadas

📊 Informes y Analítica
- ✅ Panel interactivo
- ✅ Gráficos de ingresos vs. gastos
- ✅ Análisis por categoría
- ✅ Comparativas mensuales
- ✅ Proyecciones financieras
- ✅ Exportación de datos

🎯 Metas Financieras
- ✅ Definición de objetivos
- ✅ Seguimiento de progreso
- ✅ Notificaciones de logros
- ✅ Planificación financiera

🎨 Interfaz y UX
- ✅ Diseño moderno e intuitivo
- ✅ Temas claro y oscuro
- ✅ Animaciones fluidas
- ✅ Responsivo para todos los dispositivos
- ✅ Soporte para múltiples idiomas (preparado)
⸻
🚀 Stack Tecnológico

Frontend Móvil (Ver documentación completa)
Tecnología	Versión	Descripción
React Native	0.79.2	Framework móvil
Expo	~53.0.0	Plataforma de desarrollo
TypeScript	5.3.3	Superset de JavaScript
Expo Router	~5.0.7	Enrutamiento basado en archivos
NativeWind	4.1.19	TailwindCSS para React Native
Firebase	11.6.1	Backend as a Service
React Native Reanimated	3.17.4	Animaciones nativas
Axios	1.9.0	Cliente HTTP
AsyncStorage	2.1.2	Almacenamiento local

Backend API (Ver documentación completa)
Tecnología	Versión	Descripción
Go	1.24.0	Lenguaje de programación
Chi Router	5.2.1	Router HTTP
Firebase Admin SDK	4.13.0	Autenticación y gestión
Cloud Firestore	1.17.0	Base de datos NoSQL
Google Cloud APIs	0.230.0	Servicios de Google Cloud
UUID	1.6.0	Generador de IDs únicos
godotenv	1.5.1	Variables de entorno

Infraestructura y DevOps

- Firebase Authentication - Autenticación y autorización
- Cloud Firestore - Base de datos NoSQL escalable
- Git - Control de versiones
- Make - Automatización de comandos
- Docker - Contenedores (opcional)
- Docker Compose - Orquestación de contenedores
⸻
📁 Estructura del Proyecto

kairos/
├── frontend/                   # Aplicación móvil (React Native + Expo)
│   ├── src/
│   │   ├── app/               # Rutas y pantallas (enrutamiento basado en archivos)
│   │   ├── components/        # Componentes reutilizables
│   │   ├── services/          # Servicios y llamadas a la API
│   │   ├── hooks/             # Hooks personalizados
│   │   ├── contexts/          # Contextos de React
│   │   ├── assets/            # Imágenes, iconos, fuentes
│   │   ├── utils/             # Utilidades
│   │   └── theme/             # Configuración de temas
│   ├── Makefile               # Comandos del frontend
│   ├── package.json           # Dependencias de Node.js
│   └── README.md              # Documentación del frontend
│
├── backend/                    # API REST (Go + Firebase)
│   ├── cmd/
│   │   └── app/               # Punto de entrada
│   ├── internal/
│   │   ├── domain/            # Entidades e interfaces
│   │   ├── dto/               # Data Transfer Objects (Objetos de Transferencia de Datos)
│   │   ├── repository/        # Capa de datos
│   │   ├── services/          # Lógica de negocio
│   │   ├── infrastructure/    # Implementaciones de infraestructura
│   │   └── web/               # Controladores, middlewares, servidor
│   ├── Makefile               # Comandos del backend
│   ├── go.mod                 # Dependencias de Go
│   └── README.md              # Documentación del backend
│
├── docs/                       # Documentación del proyecto
│   ├── *.png                  # Capturas de pantalla
│   ├── SOW.md                 # Statement of Work (Declaración de Trabajo)
│   └── ux.html                # Diseño UX
│
├── .gitignore                  # Archivos ignorados por Git
├── docker-compose.yaml         # Orquestación de Docker
└── README.md                   # Este archivo

⸻
✅ Requisitos Previos

General
- Git - Control de versiones
- Node.js (v18+) - Entorno de ejecución de JavaScript
- Go (v1.24+) - Lenguaje del backend
- Make - Automatización de comandos
- Cuenta en Firebase

Frontend
- Yarn o npm
- Expo CLI
- Xcode (para iOS)
- Android Studio (para Android)

Backend
- Air (opcional, recarga en vivo)
- golangci-lint (opcional, linting)
⸻
📥 Instalación

Clonar el repositorio

git clone https://github.com/tu-usuario/kairos.git
cd kairos


Instalar las dependencias

Frontend
cd frontend
make install
# o
yarn install


Backend
cd backend
make install
# o
go mod download

⸻
⚙️ Configuración

1. Configurar Firebase

1. Crea un proyecto en la Firebase Console
2. Activa Authentication (Email/Password, Google, Apple)
3. Activa Firestore Database
4. Descarga as credenciales:
    - Service Account Key (JSON) para el backend
    - Config Web para el frontend

2. Configurar las variables de entorno

Frontend
cd frontend
cp .env.example .env
# Edita el archivo .env con tus credenciales de Firebase


Backend
cd backend
make init-env
# o
cp .env.example .env
# Edita el archivo .env con tus credenciales de Firebase

⸻
🏃 Ejecución del Proyecto

Desarrollo Local

Terminal 1: Backend
cd backend
make dev
# o
make run


El backend estará funcionando en http://localhost:8080

Terminal 2: Frontend
cd frontend
make start
# o
yarn start


Ejecutar en Dispositivo/Emulador
# Android
make android

# iOS
make ios

# Web
make web


Usando Docker Compose

# En la raíz del proyecto
docker-compose up

⸻
📸 Capturas de Pantalla

<div align="center">
  <img src="./docs/login.png" width="200" alt="Login"/>
  <img src="./docs/home.png" width="200" alt="Inicio"/>
  <img src="./docs/transactions.png" width="200" alt="Transacciones"/>
  <img src="./docs/accounts.png" width="200" alt="Cuentas"/>
</div>


<div align="center">
  <img src="./docs/reports.png" width="200" alt="Informes"/>
  <img src="./docs/profile.png" width="200" alt="Perfil"/>
  <img src="./docs/onboarding.png" width="200" alt="Onboarding"/>
</div>

⸻
📚 Documentación

Documentación Técnica

- Frontend README - Guía completa de la aplicación móvil
- Backend README - Guía completa de la API REST
- Statement of Work - Alcance y requisitos del proyecto

Comandos Rápidos

Frontend
cd frontend
make help          # Lista todos los comandos
make start         # Inicia el servidor de Expo
make android       # Ejecuta en Android
make ios           # Ejecuta en iOS
make test          # Ejecuta pruebas
make lint          # Ejecuta linter


Backend
cd backend
make help          # Lista todos los comandos
make run           # Ejecuta el servidor
make dev           # Ejecuta con recarga en vivo
make test          # Ejecuta pruebas
make build         # Compila la aplicación
make verify        # Verifica la calidad del código

⸻
🗺️ Hoja de Ruta

✅ Versión 1.0 (Actual)
- [x] Autenticación completa
- [x] CRUD de transações
- [x] CRUD de contas
- [x] CRUD de categorias
- [x] Panel básico
- [x] Informes simples

🚧 Versión 1.1 (En Desarrollo)
- [ ] Metas financieras
- [ ] Notificaciones push
- [ ] Copia de seguridad y sincronización
- [ ] Modo fuera de línea (offline)

📋 Versión 2.0 (Planificado)
- [ ] Integración con Open Banking
- [ ] Importación de OFX/CSV
- [ ] Reconocimiento de recibos (OCR)
- [ ] Asistente financiero con IA
- [ ] Multidivisa
- [ ] Planificación de presupuestos
- [ ] Cuentas compartidas
- [ ] Informes avanzados
- [ ] Exportación a PDF
- [ ] API pública
⸻
🤝 Contribución

¡Las contribuciones son siempre bienvenidas! Aquí tienes cómo puedes ayudar:

Cómo Contribuir

1. Haz un Fork del proyecto
2. Clona tu fork
3. Crea una rama para tu funcionalidad (git checkout -b feature/MiFuncionalidad)
4. Haz commit de tus cambios (git commit -m 'feat: agrega MiFuncionalidad')
5. Haz push a la rama (git push origin feature/MiFuncionalidad)
6. Abre un Pull Request

Directrices

- Sigue los estándares de código del proyecto
- Escribe pruebas para las nuevas funcionalidades
- Actualiza la documentación cuando sea necesario
- Usa commits semánticos (feat, fix, docs, etc.)
- Sé respetuoso y constructivo en los comentarios

Commits Semánticos

feat: nueva funcionalidad
fix: corrección de errores
docs: documentación
style: formato, puntos y comas, etc.
refactor: refactorización de código
test: adición o modificación de pruebas
chore: actualización de dependencias, build, etc.

⸻
📄 Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.
⸻
👥 Equipo

- [Tu Nombre] - Desarrollador Full Stack - @tu-usuario
⸻
🙏 Agradecimientos

- Expo - Increíble plataforma para el desarrollo con React Native
- Go - Lenguaje potente y eficiente
- Firebase - Backend as a Service completo
- React Native - Framework móvil multiplataforma
- Comunidad de código abierto por todas las bibliotecas increíbles
⸻
📞 Contacto

- Correo electrónico: contacto@kairos.app
- Sitio web: www.kairos.app
- GitHub: @tu-usuario
- LinkedIn: Tu Nombre
⸻
<div align="center">
  <p>⭐ Si este proyecto te resultó útil, ¡considera darle una estrella!</p>
  <p>Hecho con ❤️ por el equipo de Kairos</p>
  <p>© 2026 Kairos - Todos los derechos reservados</p>
</div>
