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
📋 Table of Contents

- About the Project
- Architecture
- Features
- Tech Stack
- Project Structure
- Prerequisites
- Installation
- Configuration
- Running the Project
- Screenshots
- Documentation
- Roadmap
- Contributing
- License
⸻
📖 About the Project

Kairos is a comprehensive personal financial management solution that allows users to control their finances intelligently and intuitively. The project consists of:

- 📱 Multiplatform Mobile App (iOS, Android, Web) - React Native + Expo
- 🚀 Backend REST API - Go + Firebase + Cloud Firestore
- 🔐 Secure Authentication System - Firebase Authentication
- 📊 Financial Analysis Dashboard - Interactive charts and reports

Why Kairos?

In Greek mythology, Kairos represents the right moment, the perfect opportunity. Much like the mythological concept, our app helps you make financial decisions at the right time, with the right information.
⸻
🏗️ Architecture

The project follows a microservices architecture with a clear separation between frontend and backend:

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
│ Authentication │            │   (NoSQL Database)  │
└────────────────┘            └─────────────────────┘


Architectural Principles

- ✅ Clean Architecture in the backend (Go)
- ✅ Component-Based in the frontend (React Native)
- ✅ RESTful API for communication
- ✅ File-based Routing with Expo Router
- ✅ Type Safety with TypeScript and Go
- ✅ Dependency Injection and Inversion of Control
- ✅ Repository Pattern for data abstraction
⸻
✨ Features

🔐 Authentication & Security
- ✅ Email and password login
- ✅ Social login (Google, Apple)
- ✅ Password recovery
- ✅ JWT Authentication with Firebase
- ✅ Session persistence
- ✅ Authorization middleware

💰 Transaction Management
- ✅ Income and expense registration
- ✅ Customizable categorization
- ✅ Advanced filters (period, category, account)
- ✅ Search and sorting
- ✅ Transaction editing and deletion
- ✅ Full history

🏦 Bank Accounts
- ✅ Multiple accounts (checking, savings, investment)
- ✅ Support for major Brazilian banks
- ✅ Real-time balance
- ✅ Inter-account transfers
- ✅ Custom categories

📊 Reports & Analytics
- ✅ Interactive dashboard
- ✅ Income vs. Expense charts
- ✅ Analysis by category
- ✅ Monthly comparisons
- ✅ Financial projections
- ✅ Data export

🎯 Financial Goals
- ✅ Objective setting
- ✅ Progress tracking
- ✅ Achievement notifications
- ✅ Financial planning

🎨 Interface & UX
- ✅ Modern and intuitive design
- ✅ Light and dark theme
- ✅ Fluid animations
- ✅ Responsive for all devices
- ✅ Multi-language support (ready)
⸻
🚀 Tech Stack

Frontend Mobile (See full documentation)
Technology	Version	Description
React Native	0.79.2	Mobile framework
Expo	~53.0.0	Development platform
TypeScript	5.3.3	JavaScript superset
Expo Router	~5.0.7	File-based routing
NativeWind	4.1.19	TailwindCSS for React Native
Firebase	11.6.1	Backend as a Service
React Native Reanimated	3.17.4	Native animations
Axios	1.9.0	HTTP client
AsyncStorage	2.1.2	Local storage

Backend API (See full documentation)
Technology	Version	Description
Go	1.24.0	Programming language
Chi Router	5.2.1	HTTP Router
Firebase Admin SDK	4.13.0	Authentication and management
Cloud Firestore	1.17.0	NoSQL database
Google Cloud APIs	0.230.0	Google Cloud services
UUID	1.6.0	Unique ID generator
godotenv	1.5.1	Environment variables

Infrastructure & DevOps

- Firebase Authentication - Authentication and authorization
- Cloud Firestore - Scalable NoSQL database
- Git - Version control
- Make - Command automation
- Docker - Containerization (optional)
- Docker Compose - Container orchestration
⸻
📁 Project Structure

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

⸻
✅ Prerequisites

General
- Git - Version control
- Node.js (v18+) - JavaScript runtime
- Go (v1.24+) - Backend language
- Make - Command automation
- Firebase account

Frontend
- Yarn or npm
- Expo CLI
- Xcode (for iOS)
- Android Studio (for Android)

Backend
- Air (optional, live reload)
- golangci-lint (optional, linting)
⸻
📥 Installation

Clone the repository

git clone https://github.com/your-username/kairos.git
cd kairos


Install dependencies

Frontend
cd frontend
make install
# or
yarn install


Backend
cd backend
make install
# or
go mod download

⸻
⚙️ Configuration

1. Set up Firebase

1. Create a project in the Firebase Console
2. Enable Authentication (Email/Password, Google, Apple)
3. Enable Firestore Database
4. Download credentials:
    - Service Account Key (JSON) for the backend
    - Web Config for the frontend

2. Configure environment variables

Frontend
cd frontend
cp .env.example .env
# Edit the .env file with your Firebase credentials


Backend
cd backend
make init-env
# or
cp .env.example .env
# Edit the .env file with your Firebase credentials

⸻
🏃 Running the Project

Local Development

Terminal 1: Backend
cd backend
make dev
# or
make run


The backend will be running at http://localhost:8080

Terminal 2: Frontend
cd frontend
make start
# or
yarn start


Run on Device/Emulator
# Android
make android

# iOS
make ios

# Web
make web


Using Docker Compose

# In the project root
docker-compose up

⸻
📸 Screenshots

<div align="center">
  <img src="./docs/login.png" width="200" alt="Login"/>
  <img src="./docs/home.png" width="200" alt="Home"/>
  <img src="./docs/transactions.png" width="200" alt="Transactions"/>
  <img src="./docs/accounts.png" width="200" alt="Accounts"/>
</div>


<div align="center">
  <img src="./docs/reports.png" width="200" alt="Reports"/>
  <img src="./docs/profile.png" width="200" alt="Profile"/>
  <img src="./docs/onboarding.png" width="200" alt="Onboarding"/>
</div>

⸻
📚 Documentation

Technical Documentation

- Frontend README - Complete mobile app guide
- Backend README - Complete REST API guide
- Statement of Work - Project scope and requirements

Quick Commands

Frontend
cd frontend
make help          # List all commands
make start         # Start Expo server
make android       # Run on Android
make ios           # Run on iOS
make test          # Run tests
make lint          # Run linter


Backend
cd backend
make help          # List all commands
make run           # Run server
make dev           # Run with live reload
make test          # Run tests
make build         # Build application
make verify        # Verify code quality

⸻
🗺️ Roadmap

✅ Version 1.0 (Current)
- [x] Full authentication
- [x] Transactions CRUD
- [x] Accounts CRUD
- [x] Categories CRUD
- [x] Basic dashboard
- [x] Simple reports

🚧 Version 1.1 (In Development)
- [ ] Financial goals
- [ ] Push notifications
- [ ] Backup and sync
- [ ] Offline mode

📋 Version 2.0 (Planned)
- [ ] Open Banking integration
- [ ] OFX/CSV import
- [ ] Receipt recognition (OCR)
- [ ] AI financial assistant
- [ ] Multi-currency
- [ ] Budget planning
- [ ] Shared accounts
- [ ] Advanced reports
- [ ] PDF export
- [ ] Public API
⸻
🤝 Contributing

Contributions are always welcome! Here's how you can help:

How to Contribute

1. Fork the project
2. Clone your fork
3. Create a branch for your feature (git checkout -b feature/MyFeature)
4. Commit your changes (git commit -m 'feat: add MyFeature')
5. Push to the branch (git push origin feature/MyFeature)
6. Open a Pull Request

Guidelines

- Follow the project's code standards
- Write tests for new features
- Update documentation when necessary
- Use semantic commits (feat, fix, docs, etc.)
- Be respectful and constructive in comments

Semantic Commits

feat: new feature
fix: bug fix
docs: documentation
style: formatting, semicolons, etc.
refactor: code refactor
test: addition or modification of tests
chore: dependency updates, build, etc.

⸻
📄 License

This project is under the MIT license. See the LICENSE file for more details.
⸻
👥 Team

- [Your Name] - Full Stack Developer - @your-username
⸻
🙏 Acknowledgments

- Expo - Amazing platform for React Native development
- Go - Powerful and efficient language
- Firebase - Complete Backend as a Service
- React Native - Multiplatform mobile framework
- Open source community for all the amazing libraries
⸻
📞 Contact

- Email: contact@kairos.app
- Website: www.kairos.app
- GitHub: @your-username
- LinkedIn: Your Name
⸻
<div align="center">
  <p>⭐ If this project was useful to you, consider giving it a star!</p>
  <p>Made with ❤️ by the Kairos team</p>
  <p>© 2026 Kairos - All rights reserved</p>
</div>
