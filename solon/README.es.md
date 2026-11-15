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
