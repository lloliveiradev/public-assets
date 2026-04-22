#### Visit the website at the link: [https://heavenly-shadows.web.app/](https://heavenly-shadows.web.app/)

## 📚 About the project

**Heavenly Shadows** is a literary website dedicated to the poetry collection *Sombras de um Vislumbre Celeste* (*Shadows of a Celestial Glimpse*), by **Leo L. Oliveira**. The platform offers a unique visual, interactive experience to explore the author’s different poetic styles and personae.

## 🛠️ Tech stack

### Frontend
- [Next.js 15](https://nextjs.org) — React framework for web applications
- [React 19](https://reactjs.org) — JavaScript library for user interfaces
- [TailwindCSS 4](https://tailwindcss.com) — Utility-first CSS framework
- [Framer Motion](https://www.framer.com/motion/) — Animation library
- [ShadCN](https://ui.shadcn.com) — Modern UI components
- [React Query](https://tanstack.com/query/latest) — State management and caching
- [React Hook Form](https://react-hook-form.com) — Form handling
- [Zod](https://zod.dev) — Schema validation

### Backend
- [Firebase Firestore](https://firebase.google.com/docs/firestore) — NoSQL database
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) — SDK for authentication and management
- [MailerSend](https://www.mailersend.com) — Email delivery service

### Infrastructure
- [Vercel](https://vercel.com) — Hosting and continuous deployment (CD)

## 🎨 Project structure

```bash
heavenly-shadows/
├── app/            # App pages and routes
│   ├── api/        # API routes
│   ├── actions/   # Server Actions
│   ├── components/# Reusable components
│   ├── hooks/     # Custom hooks
│   ├── lib/       # Utilities and config
│   ├── services/  # External services
│   ├── types/     # Type definitions
│   └── styles/    # Global styles
```

## 🚀 Getting started

### Prerequisites
- Node.js (version 16 or higher)
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone [REPOSITORY_URL]
cd heavenly-shadows
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
# .env.local
FIREBASE_PRIVATE_KEY=your-private-key
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_CLIENT_EMAIL=your-client-email
MAILER_SEND_KEY=your-mailer-send-key
```

4. Start the development server:
```bash
npm run dev
```

## 📄 License

This project is licensed under the [MIT License](LICENSE).
