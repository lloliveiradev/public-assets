#### Acesse o website através do link abaixo:
- [https://heavenly-shadows.web.app/](https://heavenly-shadows.web.app/)

## 📚 Sobre o Projeto

O **Sombras Celestes** é um site literário dedicado à coletânea de poesias *Sombras de um Vislumbre Celeste*, de **Leo L. Oliveira**. A plataforma oferece uma experiência visual e interativa única para explorar diferentes estilos e personas poéticas do autor.

## 🛠️ Tecnologias

### Frontend
- [Next.js 15](https://nextjs.org) - Framework React para aplicações web
- [React 19](https://reactjs.org) - Biblioteca JavaScript para interfaces
- [TailwindCSS 4](https://tailwindcss.com) - Framework CSS utilitário
- [Framer Motion](https://www.framer.com/motion/) - Biblioteca de animações
- [ShadCN](https://ui.shadcn.com) - Componentes UI modernos
- [React Query](https://tanstack.com/query/latest) - Gerenciamento de estado e cache
- [React Hook Form](https://react-hook-form.com) - Gerenciamento de formulários
- [Zod](https://zod.dev) - Validação de esquemas

### Backend
- [Firebase Firestore](https://firebase.google.com/docs/firestore) - Banco de dados NoSQL
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) - SDK para autenticação e gerenciamento
- [MailerSend](https://www.mailersend.com) - Serviço de envio de emails

### Infraestrutura
- [Vercel](https://vercel.com) - Plataforma de hospedagem e deploy contínuo

## 🎨 Estrutura do Projeto

```bash
heavenly-shadows/
├── app/            # Páginas e rotas da aplicação
│   ├── api/       # Endpoints da API
│   ├── actions/   # Ações do servidor
│   ├── components/# Componentes reutilizáveis
│   ├── hooks/     # Hooks personalizados
│   ├── lib/       # Utilitários e configurações
│   ├── services/  # Serviços externos
│   ├── types/     # Definições de tipos
│   └── styles/    # Estilos globais
```

## 🚀 Começando

### Pré-requisitos
- Node.js (versão 16 ou superior)
- npm ou yarn

### Instalação

1. Clone o repositório:
```bash
git clone [REPOSITORY_URL]
cd heavenly-shadows
```

2. Instale as dependências:
```bash
npm install
```

3. Configure as variáveis de ambiente:
```bash
# .env.local
FIREBASE_PRIVATE_KEY=your-private-key
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_CLIENT_EMAIL=your-client-email
MAILER_SEND_KEY=your-mailer-send-key
```

4. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

## 📄 Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).