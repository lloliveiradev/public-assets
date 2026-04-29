## 📱 About the Project

Kairos is a comprehensive personal financial management solution that allows users to control their finances intelligently and intuitively. The project consists of:

- 📱 Multiplatform Mobile App (iOS, Android, Web) - React Native + Expo
- 🚀 Backend REST API - Go + Firebase + Cloud Firestore
- 🔐 Secure Authentication System - Firebase Authentication
- 📊 Financial Analysis Dashboard - Interactive charts and reports

In Greek mythology, Kairos represents the right moment, the perfect opportunity. Much like the mythological concept, our app helps you make financial decisions at the right time, with the right information.

## 🚀 Architecture Overview

The project follows a microservices architecture with a clear separation between frontend and backend:

```bash
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

- ✅ Clean Architecture in the backend (Go)
- ✅ Component-Based in the frontend (React Native)
- ✅ RESTful API for communication
- ✅ File-based Routing with Expo Router
- ✅ Type Safety with TypeScript and Go
- ✅ Dependency Injection and Inversion of Control
- ✅ Repository Pattern for data abstraction

## 🛠️ Technologies

### Frontend
- [React Native](https://reactnative.dev) - Mobile framework
- [Expo](https://expo.dev) - Development platform
- [TypeScript](https://www.typescriptlang.org) - JavaScript superset
- [Expo Router](https://docs.expo.dev/router) - File-based routing
- [NativeWind](https://www.nativewind.dev) - TailwindCSS for React Native
- [Firebase](https://firebase.google.com) - Backend as a Service
- [React Native Reanimated](https://www.reanimated.org) - Native animations
- [Axios](https://axios-http.com) - HTTP client
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Local storage

### Backend
- [Go](https://go.dev) - Programming language
- [Chi Router](https://go-chi.io) - HTTP Router
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) - Authentication and management
- [Cloud Firestore](https://firebase.google.com/docs/firestore) - NoSQL database
- [Google Cloud APIs](https://cloud.google.com) - Google Cloud services
- [UUID](https://github.com/google/uuid) - Unique ID generator
- [godotenv](https://github.com/joho/godotenv) - Environment variables

## 🛠️ Key Features

### 🔐 Authentication & Security
- ✅ Email and password login
- ✅ Social login (Google, Apple)
- ✅ Password recovery
- ✅ JWT Authentication with Firebase
- ✅ Session persistence
- ✅ Authorization middleware

### 💰 Transaction Management
- ✅ Income and expense registration
- ✅ Customizable categorization
- ✅ Advanced filters (period, category, account)
- ✅ Search and sorting
- ✅ Transaction editing and deletion
- ✅ Full history

### 🏦 Bank Accounts
- ✅ Multiple accounts (checking, savings, investment)
- ✅ Support for major Brazilian banks
- ✅ Real-time balance
- ✅ Inter-account transfers
- ✅ Custom categories

### 📊 Reports & Analytics
- ✅ Interactive dashboard
- ✅ Income vs. Expense charts
- ✅ Analysis by category
- ✅ Monthly comparisons
- ✅ Financial projections
- ✅ Data export

### 🎯 Financial Goals
- ✅ Objective setting
- ✅ Progress tracking
- ✅ Achievement notifications
- ✅ Financial planning

### 🎨 Interface & UX
- ✅ Modern and intuitive design
- ✅ Light and dark theme
- ✅ Fluid animations
- ✅ Responsive for all devices
- ✅ Multi-language support (ready)

## 🚀 Project Structure

```bash
kairos/
├── frontend/                   # Mobile app (React Native + Expo)
│   ├── src/
│   │   ├── app/               # Routes and screens (file-based routing)
│   │   ├── components/        # Reusable components
│   │   ├── services/          # Services and API calls
│   │   ├── hooks/             # Custom hooks
│   │   ├── contexts/          # React contexts
│   │   ├── assets/            # Images, icons, fonts
│   │   ├── utils/             # Utilities
│   │   └── theme/             # Theme configuration
│   ├── Makefile               # Frontend commands
│   ├── package.json           # Node.js dependencies
│   └── README.md              # Frontend documentation
│
├── backend/                    # REST API (Go + Firebase)
│   ├── cmd/
│   │   └── app/               # Entry point
│   ├── internal/
│   │   ├── domain/            # Entities and interfaces
│   │   ├── dto/               # Data Transfer Objects
│   │   ├── repository/        # Data layer
│   │   ├── services/          # Business logic
│   │   ├── infrastructure/    # Infra implementations
│   │   └── web/               # Handlers, middlewares, server
│   ├── Makefile               # Backend commands
│   ├── go.mod                 # Go dependencies
│   └── README.md              # Backend documentation
│
├── docs/                       # Project documentation
│   ├── *.png                  # Screenshots
│   ├── SOW.md                 # Statement of Work
│   └── ux.html                # UX Design
│
├── .gitignore                  # Git ignored files
├── docker-compose.yaml         # Docker orchestration
└── README.md                   # This file
```

## 🚀 Getting Started

### Prerequisites
- [Git](https://git-scm.com) - Version control
- [Node.js](https://nodejs.org) (v18+) - JavaScript runtime
- [Go](https://go.dev) (v1.24+) - Backend language
- [Make](https://www.gnu.org/software/make) - Command automation
- [Firebase account](https://firebase.google.com)
- [Expo CLI](https://docs.expo.dev/workflow/expo-cli)
- [Xcode](https://developer.apple.com/xcode) (for iOS) or [Android Studio](https://developer.android.com/studio) (for Android)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/your-username/kairos.git
cd kairos
```

2. Install dependencies for each part:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
go mod download
```

### Configure environment variables

1. **Set up Firebase**:
    - Create a project in the Firebase Console.
    - Enable Authentication (Email/Password, Google, Apple).
    - Enable Firestore Database.
    - Download credentials (JSON service account for backend, Web config for frontend).

2. **Environment files**:
```bash
# Frontend
cd frontend
cp .env.example .env

# Backend
cd backend
cp .env.example .env
```

### Start the development servers

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

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'feat: add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
