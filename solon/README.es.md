## 📱 Acerca del Proyecto

Solon es una aplicación de notas inteligente que combina el poder de la IA con una interfaz móvil moderna. La aplicación ofrece una experiencia intuitiva para crear, organizar y gestionar notas, con funciones avanzadas como reconocimiento de voz, procesamiento de texto basado en IA y sincronización en la nube.

## 🚀 Visión General de la Arquitectura

El proyecto se estructura en tres partes principales:

### Frontend (Móvil)
- Desarrollado con React Native y Expo
- Interfaz moderna con TailwindCSS
- Enfoque *offline-first* con AsyncStorage
- Reconocimiento y transcripción de voz
- Procesamiento de texto basado en IA

### Backend (API)
- Framework NestJS
- Integración con Firebase para autenticación y base de datos
- Servicios de Google Cloud para funciones de IA
- Arquitectura de API RESTful

### Core (Compartido)
- Tipos e interfaces compartidos
- Utilidades y constantes comunes
- Lógica de negocio multiplataforma

## 🛠️ Tecnologías

### Frontend
- [Expo](https://expo.dev) - Plataforma para el desarrollo de aplicaciones React Native
- [React Native](https://reactnative.dev) - Framework de desarrollo móvil
- [TypeScript](https://www.typescriptlang.org) - Lenguaje de programación con tipos
- [TailwindCSS](https://tailwindcss.com) - Framework CSS para el estilo
- [React Navigation](https://reactnavigation.org) - Navegación entre pantallas
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Almacenamiento local
- [React Native Voice](https://github.com/react-native-voice/voice) - Reconocimiento de voz
- [Expo Router](https://docs.expo.dev/router/introduction) - Enrutamiento basado en archivos

### Backend
- [NestJS](https://nestjs.com) - Framework de Node.js
- [TypeScript](https://www.typescriptlang.org) - Lenguaje de programación con tipos
- [Firebase](https://firebase.google.com) - Plataforma de desarrollo
  - [Firestore](https://firebase.google.com/docs/firestore) - Base de datos NoSQL
  - [Firebase Auth](https://firebase.google.com/docs/auth) - Autenticación de usuarios
- [Google Cloud](https://cloud.google.com) - Servicios en la nube
  - [Google Speech-to-Text](https://cloud.google.com/speech-to-text) - API de transcripción de audio
  - [Google Generative AI](https://cloud.google.com/vertex-ai/generative-ai) - Modelo Gemini 1.5 Flash
- [Jest](https://jestjs.io) - Framework de pruebas

### Core
- [TypeScript](https://www.typescriptlang.org) - Tipos e interfaces compartidos
- [Jest](https://jestjs.io) - Utilidades de prueba

## 🛠️ Funciones Principales

### 📝 Edición de Notas
- Soporte de reconocimiento de voz
- Etiquetas y marcadores para búsquedas precisas
- Sincronización en tiempo real

### 🗂️ Organización Inteligente
- **Resumen**: Genera resúmenes concisos manteniendo las ideas principales
- **Corrección de Texto**: Corrige automáticamente errores gramaticales y ortográficos
- **Extracción de Temas**: Identifica y extrae los temas principales de las notas
- **Formalización de Texto**: Transforma el texto a un tono más formal cuando es necesario

## 📋 Mapa de Pantallas

### Autenticación
- Autenticación segura con Firebase Auth
- Inicio de sesión con correo y contraseña
- Proceso de registro sencillo

### Funciones Principales
- Panel (*dashboard*) con notas recientes
- Funcionalidad de búsqueda inteligente
- Archivo para organizar notas
- Perfil de usuario y ajustes

## 🚀 Estructura del Proyecto

```
solon/
├── frontend/         # Aplicación móvil
│   ├── app/         # Rutas y pantallas principales
│   ├── components/  # Componentes reutilizables
│   ├── assets/      # Recursos estáticos
│   ├── context/     # Contextos de React
│   ├── utils/       # Funciones de utilidad
│   ├── constants/   # Constantes y configuraciones
│   └── functions/   # Funciones de negocio
│
├── backend/         # Servidor API
│   ├── src/
│   │   ├── annotations/  # Módulo de notas
│   │   ├── auth/        # Autenticación
│   │   ├── config/      # Configuraciones globales
│   │   ├── firebase/    # Integración con Firebase
│   │   ├── gemini/      # Procesamiento de IA
│   │   ├── roles/       # Gestión de roles
│   │   ├── transcription/ # Servicios de voz
│   │   └── users/       # Gestión de usuarios
│
└── core/           # Código compartido
    └── src/        # Tipos y utilidades compartidos
```

## 🚀 Cómo Empezar

### Requisitos Previos
- Node.js (versión 18 o superior)
- npm o yarn
- Expo CLI
- Cuenta de Firebase
- Cuenta de Google Cloud
- Emulador Android/iOS o dispositivo físico

### Instalación

1. Clona el repositorio:
```bash
git clone [URL_DEL_REPOSITORIO]
cd solon
```

2. Instala las dependencias de cada parte:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
npm install

# Core
cd ../core
npm install
```

3. Configura las variables de entorno:
```bash
# Backend .env
APP_CREDENTIALS='{credenciales-google-cloud}'
API_KEY='tu-clave-api'
PROJECT_ID='tu-id-de-proyecto'
PROJECT_LOCATION='tu-ubicación'
FB_CREDENTIALS='{credenciales-firebase}'
FB_API_KEY='tu-clave-api-firebase'
```

4. Inicia los servidores de desarrollo:
```bash
# Backend
cd backend
npm run start:dev

# Frontend
cd frontend
npm start
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor, sigue estos pasos:

1. Haz un fork del proyecto
2. Crea una rama para tu función (`git checkout -b feature/FuncionIncreible`)
3. Haz commit de tus cambios (`git commit -m 'Añade una FuncionIncreible'`)
4. Haz push a la rama (`git push origin feature/FuncionIncreible`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
