## 🌐 Sobre o Projeto

O Portfolio Dev é o meu portfólio profissional, o site que você está vendo agora. Ele apresenta projetos, experiências, cursos, tecnologias e idiomas, e tudo é trilíngue: o site inteiro, textos e conteúdo, aparece em português, inglês ou espanhol a partir de uma única fonte de dados.

O conteúdo não está escrito nos componentes. Ele fica no banco de dados e é atualizado por scripts, então trocar um texto ou incluir um projeto não exige mexer no código das telas.

Site no ar: [lloliveira.dev](https://lloliveira.dev)

## 🚀 Visão Geral da Arquitetura

- **Renderização no servidor primeiro**: cada página busca e traduz os dados no servidor e entrega ao navegador apenas texto simples.
- **Ações do servidor como única porta de dados**: não existem rotas de API, e o acesso ao banco nunca chega ao navegador.
- **Tradução em três camadas**: textos da interface, conteúdo do banco e seções estruturadas do currículo.
- **Conteúdo versionado em scripts**: cada script carrega os três idiomas e pode ser executado de novo sem efeitos colaterais.

✅ Idioma na rota (`/pt`, `/en`, `/es`), sem páginas duplicadas
✅ Conteúdo localizado guardado como JSON `{ pt, en, es }` e reduzido a texto antes de chegar à tela
✅ Tema claro e escuro, com a mesma paleta de cores nos dois
✅ Imagens e README dos projetos vêm de um repositório de arquivos próprio

## 🛠️ Tecnologias

### Frontend
- [Next.js](https://nextjs.org) - Framework React com App Router
- [React](https://react.dev) - Biblioteca de interfaces
- [TypeScript](https://www.typescriptlang.org) - Tipagem estática
- [Tailwind CSS](https://tailwindcss.com) - Estilos
- [shadcn/ui](https://ui.shadcn.com), [Radix UI](https://www.radix-ui.com) e [Headless UI](https://headlessui.com) - Componentes acessíveis
- [Framer Motion](https://www.framer.com/motion) - Animações
- [next-intl](https://next-intl.dev) - Tradução em três idiomas
- [next-themes](https://github.com/pacocoursey/next-themes) - Tema claro e escuro

### Backend e dados
- [Supabase](https://supabase.com) - PostgreSQL gerenciado
- [Prisma](https://www.prisma.io) - ORM
- [React Hook Form](https://react-hook-form.com) e [Zod](https://zod.dev) - Formulários e validação
- [MailerSend](https://www.mailersend.com) - E-mail transacional

### Qualidade e entrega
- [Vercel](https://vercel.com) - Hospedagem e deploy
- [ESLint](https://eslint.org) e [Prettier](https://prettier.io) - Qualidade de código
- [Yarn](https://yarnpkg.com) - Gerenciador de pacotes

## 🛠️ Principais Recursos

### 🏠 Início e Sobre
- ✅ Apresentação com as principais tecnologias em órbita ao redor da foto
- ✅ Página Sobre contada como um rio: a rolagem conduz a história na horizontal
- ✅ Fotos com crédito aos autores

### 📄 Currículo
- ✅ Abas laterais: experiências, tecnologias, cursos e idiomas
- ✅ Mapa da carreira, com a linha subindo por área de atuação
- ✅ Detalhes de cada experiência em abas, com números em destaque
- ✅ Tecnologias com evidência de uso: desde quando, em quais experiências, cursos e projetos

### 🗂️ Projetos
- ✅ Filtro por categoria
- ✅ Cada projeto exibe o README no idioma de quem visita

### ✉️ Contato
- ✅ Formulário validado que grava no banco e envia um e-mail

## 🧭 Próximos Passos

- 🔜 Reativar o assistente de IA, com o limite de uso controlado no servidor
- 🔜 Redesenhar as demais seções do currículo (cursos e idiomas)
- 🔜 Datas e imagens para todos os projetos

## 🚀 Estrutura do Projeto

```bash
portfolio-dev/
├── app/
│   ├── [locale]/        # Páginas por idioma e layout
│   ├── actions/         # Ações do servidor (única entrada de dados)
│   ├── components/      # Componentes por funcionalidade
│   ├── lib/             # Utilitários e localização
│   └── models/          # Tipos de saída das telas
├── messages/            # Textos da interface (pt, en, es)
├── prisma/              # Schema e migrações
└── scripts/             # Scripts de conteúdo trilíngue
```

## 🚀 Começando

Pré-requisitos: Node.js com Corepack e um banco PostgreSQL (por exemplo, no Supabase).

```bash
git clone https://github.com/lloliveiradev/portfolio-dev.git
cd portfolio-dev
yarn install
npx prisma migrate dev   # cria as tabelas
yarn dev                 # abre em http://localhost:3000
```

As variáveis de ambiente e a carga inicial do conteúdo estão descritas no [repositório](https://github.com/lloliveiradev/portfolio-dev).
