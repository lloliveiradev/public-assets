# Solon - Smart Notes

<div align="center">
  <div align="center" style="background-color: #fff; padding-top: 10px; padding-bottom: 5px">
    <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/full_logo.png" alt="Solon Logo" width="150"/>
  </div>
  
  [![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)](https://expo.dev)
  [![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactnative.dev)
  [![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://nestjs.com)
  [![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
  [![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
  [![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com)
</div>

## 📱 About the Project

Solon is a smart notes application that combines the power of AI with a modern mobile interface. The app offers an intuitive experience for creating, organizing, and managing notes, with advanced features such as voice recognition, AI-powered text processing, and cloud synchronization.

## 🚀 Architecture Overview

The project is structured in three main parts:

### Frontend (Mobile)
- Built with React Native and Expo
- Modern UI with TailwindCSS
- Offline-first approach with AsyncStorage
- Voice recognition and transcription
- AI-powered text processing

### Backend (API)
- NestJS framework
- Firebase integration for authentication and database
- Google Cloud services for AI features
- RESTful API architecture

### Core (Shared)
- Shared types and interfaces
- Common utilities and constants
- Cross-platform business logic

## 🛠️ Technologies

### Frontend
- [Expo](https://expo.dev) - Platform for React Native app development
- [React Native](https://reactnative.dev) - Mobile development framework
- [TypeScript](https://www.typescriptlang.org) - Typed programming language
- [TailwindCSS](https://tailwindcss.com) - CSS framework for styling
- [React Navigation](https://reactnavigation.org) - Screen navigation
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Local storage
- [React Native Voice](https://github.com/react-native-voice/voice) - Voice recognition
- [Expo Router](https://docs.expo.dev/router/introduction) - File-based routing

### Backend
- [NestJS](https://nestjs.com) - Node.js framework
- [TypeScript](https://www.typescriptlang.org) - Typed programming language
- [Firebase](https://firebase.google.com) - Development platform
  - [Firestore](https://firebase.google.com/docs/firestore) - NoSQL database
  - [Firebase Auth](https://firebase.google.com/docs/auth) - User authentication
- [Google Cloud](https://cloud.google.com) - Cloud services
  - [Google Speech-to-Text](https://cloud.google.com/speech-to-text) - Audio transcription API
  - [Google Generative AI](https://cloud.google.com/vertex-ai/generative-ai) - Gemini 1.5 Flash model
- [Jest](https://jestjs.io) - Testing framework

### Core
- [TypeScript](https://www.typescriptlang.org) - Shared types and interfaces
- [Jest](https://jestjs.io) - Testing utilities

## 🛠️ Key Features

### 📝 Note Edition
<div align="center">
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/note.jpeg" alt="Note Edition" height="600"/>
</div>

- Voice recognition support
- Tags and markers for precise searches
- Real-time synchronization

### 🗂️ Smart Organization
<div align="center">
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/formalize.jpeg" alt="Smart Organization" height="600"/>
</div>

- **Summarization**: Generates concise summaries while maintaining key ideas
- **Text Correction**: Automatically fixes grammar and spelling errors
- **Topic Extraction**: Identifies and extracts main topics from notes
- **Text Formalization**: Transforms text to a more formal tone when needed

## 📋 Screen Mapping

### Authentication
<div align="center">
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/login.jpeg" alt="Login" height="600"/>
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/sign-up.jpeg" alt="Sign Up" height="600"/>
</div>

- Secure authentication with Firebase Auth
- Email and password login
- Simple registration process

### Main Features
<div align="center">
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/home.jpeg" alt="Home" height="600"/>
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/search.jpeg" alt="Search" height="600"/>
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/archive.jpeg" alt="Archive" height="600"/>
  <img src="https://github.com/lloliveiradev/public-assets/raw/main/solon/profile.jpeg" alt="Profile" height="600"/>
</div>

- Dashboard with recent notes
- Smart search functionality
- Archive for organizing notes
- User profile and settings

## 🚀 Project Structure

```
solon/
├── frontend/         # Mobile application
│   ├── app/         # Main routes and pages
│   ├── components/  # Reusable components
│   ├── assets/      # Static resources
│   ├── context/     # React contexts
│   ├── utils/       # Utility functions
│   ├── constants/   # Constants and configurations
│   └── functions/   # Business functions
│
├── backend/         # API server
│   ├── src/
│   │   ├── annotations/  # Notes module
│   │   ├── auth/        # Authentication
│   │   ├── config/      # Global configurations
│   │   ├── firebase/    # Firebase integration
│   │   ├── gemini/      # AI processing
│   │   ├── roles/       # Role management
│   │   ├── transcription/ # Voice services
│   │   └── users/       # User management
│
└── core/           # Shared code
    └── src/        # Shared types and utilities
```

## 🚀 Getting Started

### Prerequisites
- Node.js (version 18 or higher)
- npm or yarn
- Expo CLI
- Firebase account
- Google Cloud account
- Android/iOS emulator or physical device

### Installation

1. Clone the repository:
```bash
git clone [REPOSITORY_URL]
cd solon
```

2. Install dependencies for each part:
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

3. Configure environment variables:
```bash
# Backend .env
APP_CREDENTIALS='{google-cloud-credentials}'
API_KEY='your-api-key'
PROJECT_ID='your-project-id'
PROJECT_LOCATION='your-location'
FB_CREDENTIALS='{firebase-credentials}'
FB_API_KEY='your-firebase-api-key'
```

4. Start the development servers:
```bash
# Backend
cd backend
npm run start:dev

# Frontend
cd frontend
npm start
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.