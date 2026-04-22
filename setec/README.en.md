## 📚 About the Project

This project is a redesign proposal for the **SETEC (Serviços Técnicos Gerais)** website, an autonomous municipal agency of the City of Campinas, São Paulo. The goal is to provide a modern, intuitive, and accessible interface for citizens to efficiently access public information and services.

The project consists of a modern static website integrated into the Firebase ecosystem, focused on providing detailed information about funeral services, public transparency, advertising management in public areas, and access to official documents.

## 🛠️ Tech Stack

### Frontend
- [HTML5](https://html.spec.whatwg.org/) and [CSS3](https://www.w3.org/Style/CSS/) — Base structure and styling
- [Bootstrap 5](https://getbootstrap.com/) — CSS framework for responsive development
- [jQuery](https://jquery.com/) — JavaScript library for DOM manipulation
- [FontAwesome](https://fontawesome.com/) — Icon set
- [Google Fonts (Roboto)](https://fonts.google.com/specimen/Roboto) — Typography

### Backend and Infrastructure
- [Firebase Hosting](https://firebase.google.com/docs/hosting) — Fast and secure hosting
- [Firebase Firestore](https://firebase.google.com/docs/firestore) — Real-time NoSQL database
- [Firebase Storage](https://firebase.google.com/docs/storage) — File and document storage
- [Firebase Auth](https://firebase.google.com/docs/auth) — User authentication system

## 🗂️ Project Structure

```bash
setec-site/
├── public/                # Main site content
│   ├── assets/            # Static assets
│   │   ├── css/           # Stylesheets
│   │   ├── docs/          # Official documents and PDF forms
│   │   ├── fonts/         # Local fonts
│   │   ├── images/        # Images and logos
│   │   └── svg/           # SVG vectors and icons
│   ├── pag/               # Thematic sub-pages
│   │   ├── funeraria.html     # Funeral services and cemeteries
│   │   ├── transparencia.html # Transparency portal
│   │   ├── publicidade.html   # Advertising in public areas
│   │   ├── solo.html          # Land use management
│   │   └── covid19.html       # Specific information and protocols
│   ├── vendor/            # Third-party libraries
│   └── index.html         # Homepage
├── firebase.json          # Firebase configurations
├── firestore.rules        # Database security rules
├── storage.rules          # Storage security rules
└── README.md              # Project documentation
```

## ✨ Key Features

- **Funeral Services** — Information on cemeteries, crematoriums, and funeral plans
- **Public Transparency** — Access to agency data and financial reporting
- **Online Documentation** — Repository of forms and applications (exhumation, transfer, etc.)
- **Advertising Management** — Licensing for ads in public and private areas
- **Responsive Interface** — Adaptable design for any device

## 🚀 Getting Started

### Prerequisites
- [Firebase](https://console.firebase.google.com/) account
- [Firebase CLI](https://firebase.google.com/docs/cli) installed globally

### Installation and Deployment

1. Clone the repository:
```bash
git clone [REPOSITORY_URL]
cd setec-site
```

2. Login to Firebase and preview locally:
```bash
firebase login
firebase serve
```

3. Deploy:
```bash
firebase deploy
```

## 📄 License

This project is developed for the modernization of SETEC Campinas public services and is licensed under the [MIT License](LICENSE).
