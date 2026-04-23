## 📱 Acerca del Proyecto

Kairos es una solución integral de gestión financiera personal que permite a los usuarios controlar sus finanzas de forma inteligente e intuitiva. El proyecto está compuesto por:

- 📱 Aplicación Móvil Multiplataforma (iOS, Android, Web) - React Native + Expo
- 🚀 API REST Backend - Go + Firebase + Cloud Firestore
- 🔐 Sistema de Autenticación Seguro - Firebase Authentication
- 📊 Panel de Análisis Financiero - Gráficos e informes interactivos

En la mitología griega, Kairos representa el momento oportuno, la oportunidad perfecta. Al igual que el concepto mitológico, nuestra aplicación te ayuda a tomar decisiones financieras en el momento adecuado, con la información correcta.

## 🚀 Visión General de la Arquitectura

El proyecto sigue una arquitectura de microservicios con una clara separación entre frontend y backend:

```
┌─────────────────────────────────────────────────────────────┐
│                     Mobile Apps (iOS/Android/Web)           │
│              React Native + Expo + TypeScript               │
└───────────────────────┬─────────────────────────────────────┘
                        │ REST API
                        │ (HTTP/JSON)
┌───────────────────────▼─────────────────────────────────────┐
│                    Backend API (Go)                         │
│          Chi Router + Firebase Admin SDK                    │
└───────────────────────┬─────────────────────────────────────┘
                        │
        ┌───────────────┴────────────────┐
        │                                │
┌───────▼────────┐            ┌──────────▼──────────┐
│   Firebase     │            │   Cloud Firestore   │
│ Authentication │            │   (Database NoSQL)  │
└────────────────┘            └─────────────────────┘
```

- ✅ Clean Architecture en el backend (Go)
- ✅ Basado en Componentes en el frontend (React Native)
- ✅ API RESTful para la comunicación
- ✅ Enrutamiento basado en archivos con Expo Router
- ✅ Seguridad de Tipos con TypeScript y Go
- ✅ Inyección de Dependencias e Inversión de Control
- ✅ Patrón Repository para la abstracción de datos

## 🛠️ Tecnologías

### Frontend
- [React Native](https://reactnative.dev) - Framework móvil
- [Expo](https://expo.dev) - Plataforma de desarrollo
- [TypeScript](https://www.typescriptlang.org) - Superset de JavaScript
- [Expo Router](https://docs.expo.dev/router) - Enrutamiento basado en archivos
- [NativeWind](https://www.nativewind.dev) - TailwindCSS para React Native
- [Firebase](https://firebase.google.com) - Backend as a Service
- [React Native Reanimated](https://www.reanimated.org) - Animaciones nativas
- [Axios](https://axios-http.com) - Cliente HTTP
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Almacenamiento local

### Backend
- [Go](https://go.dev) - Lenguaje de programación
- [Chi Router](https://go-chi.io) - Router HTTP
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) - Autenticación y gestión
- [Cloud Firestore](https://firebase.google.com/docs/firestore) - Base de datos NoSQL
- [Google Cloud APIs](https://cloud.google.com) - Servicios de Google Cloud
- [UUID](https://github.com/google/uuid) - Generador de IDs únicos
- [godotenv](https://github.com/joho/godotenv) - Variables de entorno

## 🛠️ Funciones Principales

### 🔐 Autenticación y Seguridad
- ✅ Inicio de sesión con correo y contraseña
- ✅ Inicio de sesión social (Google, Apple)
- ✅ Recuperación de contraseña
- ✅ Autenticación JWT con Firebase
- ✅ Persistencia de sesión
- ✅ Middleware de autorización

### 💰 Gestión de Transacciones
- ✅ Registro de ingresos y gastos
- ✅ Categorización personalizable
- ✅ Filtros avanzados (periodo, categoría, cuenta)
- ✅ Búsqueda y ordenación
- ✅ Edición y eliminación de transacciones
- ✅ Historial completo

### 🏦 Cuentas Bancarias
- ✅ Múltiples cuentas (corriente, ahorros, inversión)
- ✅ Soporte para los principales bancos brasileños
- ✅ Saldo en tiempo real
- ✅ Transferencias entre cuentas
- ✅ Categorías personalizadas

### 📊 Informes y Analítica
- ✅ Panel interactivo
- ✅ Gráficos de ingresos vs. gastos
- ✅ Análisis por categoría
- ✅ Comparativas mensuales
- ✅ Proyecciones financieras
- ✅ Exportación de datos

### 🎯 Metas Financieras
- ✅ Definición de objetivos
- ✅ Seguimiento de progreso
- ✅ Notificaciones de logros
- ✅ Planificación financiera

### 🎨 Interfaz y UX
- ✅ Diseño moderno e intuitivo
- ✅ Temas claro y oscuro
- ✅ Animaciones fluidas
- ✅ Responsivo para todos los dispositivos
- ✅ Soporte para múltiples idiomas (preparado)

## 🚀 Estructura del Proyecto

```
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
│   │   ├── dto/               # Objetos de Transferencia de Datos (DTO)
│   │   ├── repository/        # Capa de datos
│   │   ├── services/          # Lógica de negocio
│   │   ├── infrastructure/    # Implementaciones de infraestructura
│   │   └── web/               # Handlers, middlewares, servidor
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
```

## 🚀 Cómo Empezar

### Requisitos Previos
- [Git](https://git-scm.com) - Control de versiones
- [Node.js](https://nodejs.org) (v18+) - Entorno de ejecución de JavaScript
- [Go](https://go.dev) (v1.24+) - Lenguaje del backend
- [Make](https://www.gnu.org/software/make) - Automatización de comandos
- [Cuenta en Firebase](https://firebase.google.com)
- [Expo CLI](https://docs.expo.dev/workflow/expo-cli)
- [Xcode](https://developer.apple.com/xcode) (para iOS) o [Android Studio](https://developer.android.com/studio) (para Android)

### Instalación

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/kairos.git
cd kairos
```

2. Instala las dependencias de cada parte:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
go mod download
```

### Configurar variables de entorno

1. **Configurar Firebase**:
    - Crea un proyecto en la Firebase Console.
    - Activa Authentication (Email/Password, Google, Apple).
    - Activa Firestore Database.
    - Descarga las credenciales (JSON service account para el backend, Web config para el frontend).

2. **Archivos de entorno**:
```bash
# Frontend
cd frontend
cp .env.example .env

# Backend
cd backend
cp .env.example .env
```

### Iniciar los servidores de desarrollo

1. **Backend**:
```bash
cd backend
go run cmd/app/main.go
```

2. **Frontend**:
```bash
cd frontend
npx expo start
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor, sigue estos pasos:

1. Haz un fork del proyecto
2. Crea una rama para tu función (`git checkout -b feature/AmazingFeature`)
3. Haz commit de tus cambios (`git commit -m 'feat: add AmazingFeature'`)
4. Haz push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
