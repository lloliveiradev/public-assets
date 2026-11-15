## 🌐 About the Project

Portfolio Dev is my professional portfolio, the site you are looking at right now. It presents projects, work experience, courses, technologies and languages, and everything is trilingual: the whole site, copy and content, shows up in Portuguese, English or Spanish from a single source of data.

The content is not written inside the components. It lives in the database and is updated by scripts, so changing a text or adding a project does not require touching the screen code.

Live site: [lloliveira.dev](https://lloliveira.dev)

## 🚀 Architecture Overview

- **Server-first rendering**: each page fetches and translates its data on the server and hands the browser only plain text.
- **Server Actions as the only data door**: there are no API routes, and database access never reaches the browser.
- **Translation in three layers**: interface copy, database content and structured résumé sections.
- **Content versioned in scripts**: each script carries all three languages and can be run again with no side effects.

- ✅ Language in the route (`/pt`, `/en`, `/es`), with no duplicated pages
- ✅ Localized content stored as `{ pt, en, es }` JSON and reduced to text before it reaches the screen
- ✅ Light and dark themes, with the same color palette in both
- ✅ Project images and READMEs come from a dedicated assets repository

## 🛠️ Technologies

### Frontend
- [Next.js](https://nextjs.org) - React framework with App Router
- [React](https://react.dev) - UI library
- [TypeScript](https://www.typescriptlang.org) - Static typing
- [Tailwind CSS](https://tailwindcss.com) - Styling
- [shadcn/ui](https://ui.shadcn.com), [Radix UI](https://www.radix-ui.com) and [Headless UI](https://headlessui.com) - Accessible components
- [Framer Motion](https://www.framer.com/motion) - Animations
- [next-intl](https://next-intl.dev) - Three-language translation
- [next-themes](https://github.com/pacocoursey/next-themes) - Light and dark theme

### Backend and data
- [Supabase](https://supabase.com) - Managed PostgreSQL
- [Prisma](https://www.prisma.io) - ORM
- [React Hook Form](https://react-hook-form.com) and [Zod](https://zod.dev) - Forms and validation
- [MailerSend](https://www.mailersend.com) - Transactional email

### Quality and delivery
- [Vercel](https://vercel.com) - Hosting and deploys
- [ESLint](https://eslint.org) and [Prettier](https://prettier.io) - Code quality
- [Yarn](https://yarnpkg.com) - Package manager

## 🛠️ Key Features

### 🏠 Home and About
- ✅ An introduction with the main technologies orbiting the photo
- ✅ An About page told as a river: scrolling carries the story sideways
- ✅ Photos credited to their authors

### 📄 Resume
- ✅ Side tabs: experience, technologies, courses and languages
- ✅ A career map, with the line climbing through areas of work
- ✅ Details of each experience in tabs, with figures highlighted
- ✅ Technologies with proof of use: since when, and in which experiences, courses and projects

### 🗂️ Projects
- ✅ Filter by category
- ✅ Each project shows its README in the visitor's language

### ✉️ Contact
- ✅ A validated form that saves to the database and sends an email

## 🧭 What's Next

- 🔜 Bring the AI assistant back, with the usage limit enforced on the server
- 🔜 Redesign the remaining resume sections (courses and languages)
- 🔜 Dates and images for every project

## 🚀 Project Structure

```bash
portfolio-dev/
├── app/
│   ├── [locale]/        # Pages per language and layout
│   ├── actions/         # Server Actions (the only data entry point)
│   ├── components/      # Components by feature
│   ├── lib/             # Utilities and localization
│   └── models/          # Output types for the screens
├── messages/            # Interface copy (pt, en, es)
├── prisma/              # Schema and migrations
└── scripts/             # Trilingual content scripts
```

## 🚀 Getting Started

Prerequisites: Node.js with Corepack and a PostgreSQL database (for example on Supabase).

```bash
git clone https://github.com/lloliveiradev/portfolio-dev.git
cd portfolio-dev
yarn install
npx prisma migrate dev   # creates the tables
yarn dev                 # opens at http://localhost:3000
```

The environment variables and the initial content load are described in the [repository](https://github.com/lloliveiradev/portfolio-dev).
