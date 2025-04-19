#### Acesse o website através do link abaixo:
- [https://heavenly-shadows.web.app/](https://heavenly-shadows.web.app/)

## 📚 Sobre o Projeto

O **Sombras Celestes** é um site literário dedicado à coletânea de poesias *Sombras de um Vislumbre Celeste*, de **Leo L. Oliveira**. A plataforma oferece uma experiência visual e interativa única para explorar diferentes estilos e personas poéticas do autor.

## 🛠️ Tecnologias

### Frontend
- [Next.js](https://nextjs.org) - Framework React para aplicações web
- [React.js](https://reactjs.org) - Biblioteca JavaScript para interfaces
- [TailwindCSS](https://tailwindcss.com) - Framework CSS utilitário
- [AOS](https://michalsnik.github.io/aos/) - Biblioteca de animações
- [ShadCN](https://ui.shadcn.com) - Componentes UI modernos

### Backend
- [NestJS](https://nestjs.com) - Node.js framework
- [TypeScript](https://www.typescriptlang.org) - Typed programming language
- [Firebase Firestore](https://firebase.google.com/docs/firestore) - NoSQL database

### Infraestrutura
- [Vercel](https://vercel.com) - Plataforma de hospedagem e deploy contínuo

## 🎨 Estrutura do Projeto

```
heavenly-shadows/
├── app/            # Páginas principais e rotas
│   ├── page.tsx    # Página inicial
│   └── layout.tsx  # Layout principal
├── components/     # Componentes reutilizáveis
│   ├── ui/        # Componentes de interface
│   └── sections/  # Seções da página
├── styles/        # Configurações de estilo
│   └── globals.css # Estilos globais
└── public/        # Recursos estáticos
    ├── images/    # Imagens e ícones
    └── fonts/     # Fontes personalizadas
```

## 🚀 Começando

### Pré-requisitos
- Node.js (versão 16 ou superior)
- npm ou yarn
- Conta Firebase

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
NEXT_PUBLIC_FIREBASE_API_KEY=your-api-key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your-auth-domain
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your-project-id
```

4. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

5. Para deploy na Vercel:
```bash
vercel
```

## 🌐 Acesso

O site está disponível em: [Sombras Celestes](https://heavenly-shadows.vercel.app/)

## 📄 Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).