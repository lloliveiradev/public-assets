# Portfolio Dev

Um portfólio moderno e interativo desenvolvido com Next.js, oferecendo uma experiência única para apresentar projetos e habilidades.

## 🚀 Tecnologias

- **Framework**: [Next.js 15.2.3](https://nextjs.org/) com App Router
- **Linguagem**: [TypeScript](https://www.typescriptlang.org/)
- **Estilização**: [TailwindCSS 4](https://tailwindcss.com/)
- **Banco de Dados**: 
  - [Supabase](https://supabase.com) com PostgreSQL
  - [Prisma](https://www.prisma.io/) como ORM
- **UI/UX**: 
  - [Shadcn/ui](https://ui.shadcn.com/) para componentes reutilizáveis
  - [Framer Motion](https://www.framer.com/motion/) para animações
  - [Radix UI](https://www.radix-ui.com/) para componentes acessíveis
  - [Headless UI](https://headlessui.com/) para componentes sem estilos
- **Formulários**: [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/)
- **IA**: [Google Generative AI](https://ai.google.dev/)
- **Email**: [Mailersend](https://www.mailersend.com/)

## 📁 Estrutura do Projeto

```
app/
├── components/     # Componentes reutilizáveis
├── (pages)/       # Páginas da aplicação
├── lib/           # Utilitários e configurações
├── models/        # Modelos de dados
├── actions/       # Ações do servidor
├── api/           # Endpoints da API
├── hooks/         # Hooks personalizados
└── types/         # Definições de tipos
```

## 🛠️ Pré-requisitos

- Node.js (versão recomendada: 18+)
- npm, yarn ou pnpm
- Git

## 🔧 Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/portfolio-dev.git
cd portfolio-dev
```

2. Instale as dependências:
```bash
npm install
# ou
yarn install
# ou
pnpm install
```

3. Configure as variáveis de ambiente:
```bash
cp .env.example .env.local
```
Edite o arquivo `.env.local` com suas configurações.

4. Execute as migrações do banco de dados:
```bash
npx prisma migrate dev
```

## 🚀 Executando o Projeto

Para desenvolvimento:
```bash
npm run dev
# ou
yarn dev
# ou
pnpm dev
```

Para produção:
```bash
npm run build
npm start
# ou
yarn build
yarn start
# ou
pnpm build
pnpm start
```

## 📦 Scripts Disponíveis

- `dev`: Inicia o servidor de desenvolvimento
- `build`: Gera o build de produção
- `start`: Inicia o servidor de produção
- `lint`: Executa o linter
- `format`: Formata o código usando Prettier

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 📞 Suporte

Para suporte, envie um email para seu-email@exemplo.com ou abra uma issue no repositório.
