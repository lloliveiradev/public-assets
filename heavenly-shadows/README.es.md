#### Accede al sitio web mediante el enlace: [https://heavenly-shadows.web.app/](https://heavenly-shadows.web.app/)

## 📚 Acerca del proyecto

**Sombras celestes** es un sitio web literario dedicado a la recopilación de poesía *Sombras de um Vislumbre Celeste* (*Sombras de un atisbo celeste*), de **Leo L. Oliveira**. La plataforma ofrece una experiencia visual e interactiva única para explorar los distintos estilos y personas poéticas del autor.

## 🛠️ Stack tecnológico

### Frontend
- [Next.js 15](https://nextjs.org) — Framework React para aplicaciones web
- [React 19](https://reactjs.org) — Biblioteca JavaScript para interfaces de usuario
- [TailwindCSS 4](https://tailwindcss.com) — Framework CSS de utilidades (*utility-first*)
- [Framer Motion](https://www.framer.com/motion/) — Biblioteca de animación
- [ShadCN](https://ui.shadcn.com) — Componentes de UI modernos
- [React Query](https://tanstack.com/query/latest) — Gestión de estado y caché
- [React Hook Form](https://react-hook-form.com) — Manejo de formularios
- [Zod](https://zod.dev) — Validación de esquemas (*schema*)

### Backend
- [Firebase Firestore](https://firebase.google.com/docs/firestore) — Base de datos NoSQL
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) — SDK para autenticación y administración
- [MailerSend](https://www.mailersend.com) — Servicio de envío de correo

### Infraestructura
- [Vercel](https://vercel.com) — Plataforma de alojamiento y *deploy* continuo (CI/CD)

## 🎨 Estructura del proyecto

```bash
heavenly-shadows/
├── app/            # Páginas y rutas de la app
│   ├── api/        # Rutas de la API
│   ├── actions/   # Server Actions
│   ├── components/# Componentes reutilizables
│   ├── hooks/     # Hooks personalizados
│   ├── lib/       # Utilidades y configuración
│   ├── services/  # Servicios externos
│   ├── types/     # Definiciones de tipos
│   └── styles/    # Estilos globales
```

## 🚀 Cómo empezar

### Requisitos previos
- Node.js (versión 16 o superior)
- npm o yarn

### Instalación

1. Clona el repositorio:
```bash
git clone [REPOSITORY_URL]
cd heavenly-shadows
```

2. Instala las dependencias:
```bash
npm install
```

3. Configura las variables de entorno:
```bash
# .env.local
FIREBASE_PRIVATE_KEY=your-private-key
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_CLIENT_EMAIL=your-client-email
MAILER_SEND_KEY=your-mailer-send-key
```

4. Inicia el servidor de desarrollo:
```bash
npm run dev
```

## 📄 Licencia

Este proyecto está licenciado bajo la [licencia MIT](LICENSE).
