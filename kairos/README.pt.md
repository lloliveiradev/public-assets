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
📋 Índice

- Sobre o Projeto
- Arquitetura
- Funcionalidades
- Stack Tecnológico
- Estrutura do Projeto
- Pré-requisitos
- Instalação
- Configuração
- Executando o Projeto
- Screenshots
- Documentação
- Roadmap
- Contribuindo
- Licença
⸻
📖 Sobre o Projeto

Kairos é uma solução completa de gerenciamento financeiro pessoal que permite aos usuários controlar suas finanças de forma inteligente e intuitiva. O projeto é composto por:

- 📱 Aplicativo Mobile Multiplataforma (iOS, Android, Web) - React Native + Expo
- 🚀 API REST Backend - Go + Firebase + Cloud Firestore
- 🔐 Sistema de Autenticação Seguro - Firebase Authentication
- 📊 Dashboard de Análise Financeira - Gráficos e relatórios interativos

Por que Kairos?

Na mitologia grega, Kairos representa o momento certo, a oportunidade perfeita. Assim como o conceito mitológico, nosso aplicativo ajuda você a tomar decisões financeiras no momento certo, com as informações certas.
⸻
🏗️ Arquitetura

O projeto segue uma arquitetura de microserviços com separação clara entre frontend e backend:

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


Princípios Arquiteturais

- ✅ Clean Architecture no backend (Go)
- ✅ Component-Based no frontend (React Native)
- ✅ RESTful API para comunicação
- ✅ File-based Routing com Expo Router
- ✅ Type Safety com TypeScript e Go
- ✅ Dependency Injection e inversão de controle
- ✅ Repository Pattern para abstração de dados
⸻
✨ Funcionalidades

🔐 Autenticação & Segurança
- ✅ Login com email e senha
- ✅ Login social (Google, Apple)
- ✅ Recuperação de senha
- ✅ Autenticação JWT com Firebase
- ✅ Persistência de sessão
- ✅ Middleware de autorização

💰 Gestão de Transações
- ✅ Cadastro de receitas e despesas
- ✅ Categorização personalizável
- ✅ Filtros avançados (período, categoria, conta)
- ✅ Busca e ordenação
- ✅ Edição e exclusão de transações
- ✅ Histórico completo

🏦 Contas Bancárias
- ✅ Múltiplas contas (corrente, poupança, investimento)
- ✅ Suporte aos principais bancos brasileiros
- ✅ Saldo em tempo real
- ✅ Transferências entre contas
- ✅ Categorias personalizadas

📊 Relatórios & Analytics
- ✅ Dashboard interativo
- ✅ Gráficos de receitas vs despesas
- ✅ Análise por categoria
- ✅ Comparativos mensais
- ✅ Projeções financeiras
- ✅ Exportação de dados

🎯 Metas Financeiras
- ✅ Definição de objetivos
- ✅ Acompanhamento de progresso
- ✅ Notificações de conquistas
- ✅ Planejamento financeiro

🎨 Interface & UX
- ✅ Design moderno e intuitivo
- ✅ Tema claro e escuro
- ✅ Animações fluidas
- ✅ Responsivo para todos os dispositivos
- ✅ Suporte a múltiplos idiomas (preparado)
⸻
🚀 Stack Tecnológico

Frontend Mobile (Ver documentação completa)
Tecnologia	Versão	Descrição
React Native	0.79.2	Framework mobile
Expo	~53.0.0	Plataforma de desenvolvimento
TypeScript	5.3.3	Superset JavaScript
Expo Router	~5.0.7	Roteamento file-based
NativeWind	4.1.19	TailwindCSS para React Native
Firebase	11.6.1	Backend as a Service
React Native Reanimated	3.17.4	Animações nativas
Axios	1.9.0	Cliente HTTP
AsyncStorage	2.1.2	Armazenamento local

Backend API (Ver documentação completa)
Tecnologia	Versão	Descrição
Go	1.24.0	Linguagem de programação
Chi Router	5.2.1	Router HTTP
Firebase Admin SDK	4.13.0	Autenticação e gerenciamento
Cloud Firestore	1.17.0	Banco de dados NoSQL
Google Cloud APIs	0.230.0	Serviços Google Cloud
UUID	1.6.0	Gerador de IDs únicos
godotenv	1.5.1	Variáveis de ambiente

Infraestrutura & DevOps

- Firebase Authentication - Autenticação e autorização
- Cloud Firestore - Banco de dados NoSQL escalável
- Git - Controle de versão
- Make - Automação de comandos
- Docker - Containerização (opcional)
- Docker Compose - Orquestração de containers
⸻
📁 Estrutura do Projeto

kairos/
├── frontend/                   # Aplicativo mobile (React Native + Expo)
│   ├── src/
│   │   ├── app/               # Rotas e telas (file-based routing)
│   │   ├── components/        # Componentes reutilizáveis
│   │   ├── services/          # Serviços e API calls
│   │   ├── hooks/             # Custom hooks
│   │   ├── contexts/          # Contextos React
│   │   ├── assets/            # Imagens, ícones, fontes
│   │   ├── utils/             # Utilitários
│   │   └── theme/             # Configuração de tema
│   ├── Makefile               # Comandos frontend
│   ├── package.json           # Dependências Node.js
│   └── README.md              # Documentação frontend
│
├── backend/                    # API REST (Go + Firebase)
│   ├── cmd/
│   │   └── app/               # Ponto de entrada
│   ├── internal/
│   │   ├── domain/            # Entidades e interfaces
│   │   ├── dto/               # Data Transfer Objects
│   │   ├── repository/        # Camada de dados
│   │   ├── services/          # Lógica de negócio
│   │   ├── infrastructure/    # Implementações de infra
│   │   └── web/               # Handlers, middlewares, server
│   ├── Makefile               # Comandos backend
│   ├── go.mod                 # Dependências Go
│   └── README.md              # Documentação backend
│
├── docs/                       # Documentação do projeto
│   ├── *.png                  # Screenshots
│   ├── SOW.md                 # Statement of Work
│   └── ux.html                # Design UX
│
├── .gitignore                  # Arquivos ignorados pelo Git
├── docker-compose.yaml         # Orquestração Docker
└── README.md                   # Este arquivo

⸻
✅ Pré-requisitos

Geral
- Git - Controle de versão
- Node.js (v18+) - Runtime JavaScript
- Go (v1.24+) - Linguagem do backend
- Make - Automação de comandos
- Conta no Firebase

Frontend
- Yarn ou npm
- Expo CLI
- Xcode (para iOS)
- Android Studio (para Android)

Backend
- Air (opcional, live reload)
- golangci-lint (opcional, linting)
⸻
📥 Instalação

Clone o repositório

git clone https://github.com/seu-usuario/kairos.git
cd kairos


Instale as dependências

Frontend
cd frontend
make install
# ou
yarn install


Backend
cd backend
make install
# ou
go mod download

⸻
⚙️ Configuração

1. Configure o Firebase

1. Crie um projeto no Firebase Console
2. Ative o Authentication (Email/Password, Google, Apple)
3. Ative o Firestore Database
4. Baixe as credenciais:
    - Service Account Key (JSON) para o backend
    - Config Web para o frontend

2. Configure as variáveis de ambiente

Frontend
cd frontend
cp .env.example .env
# Edite o arquivo .env com suas credenciais Firebase


Backend
cd backend
make init-env
# ou
cp .env.example .env
# Edite o arquivo .env com suas credenciais Firebase

⸻
🏃 Executando o Projeto

Desenvolvimento Local

Terminal 1: Backend
cd backend
make dev
# ou
make run


O backend estará rodando em http://localhost:8080

Terminal 2: Frontend
cd frontend
make start
# ou
yarn start


Executar no Dispositivo/Emulador
# Android
make android

# iOS
make ios

# Web
make web


Usando Docker Compose

# Na raiz do projeto
docker-compose up

⸻
📸 Screenshots

<div align="center">
  <img src="./docs/login.png" width="200" alt="Login"/>
  <img src="./docs/home.png" width="200" alt="Home"/>
  <img src="./docs/transactions.png" width="200" alt="Transações"/>
  <img src="./docs/accounts.png" width="200" alt="Contas"/>
</div>


<div align="center">
  <img src="./docs/reports.png" width="200" alt="Relatórios"/>
  <img src="./docs/profile.png" width="200" alt="Perfil"/>
  <img src="./docs/onboarding.png" width="200" alt="Onboarding"/>
</div>

⸻
📚 Documentação

Documentação Técnica

- Frontend README - Guia completo do aplicativo mobile
- Backend README - Guia completo da API REST
- Statement of Work - Escopo e requisitos do projeto

Comandos Rápidos

Frontend
cd frontend
make help          # Lista todos os comandos
make start         # Inicia servidor Expo
make android       # Executa no Android
make ios           # Executa no iOS
make test          # Executa testes
make lint          # Executa linter


Backend
cd backend
make help          # Lista todos os comandos
make run           # Executa servidor
make dev           # Executa com live reload
make test          # Executa testes
make build         # Compila aplicação
make verify        # Verifica qualidade do código

⸻
🗺️ Roadmap

✅ Versão 1.0 (Atual)
- [x] Autenticação completa
- [x] CRUD de transações
- [x] CRUD de contas
- [x] CRUD de categorias
- [x] Dashboard básico
- [x] Relatórios simples

🚧 Versão 1.1 (Em Desenvolvimento)
- [ ] Metas financeiras
- [ ] Notificações push
- [ ] Backup e sincronização
- [ ] Modo offline

📋 Versão 2.0 (Planejado)
- [ ] Integração com Open Banking
- [ ] Importação de OFX/CSV
- [ ] Reconhecimento de recibos (OCR)
- [ ] Assistente financeiro com IA
- [ ] Multi-moedas
- [ ] Planejamento de orçamento
- [ ] Compartilhamento de contas
- [ ] Relatórios avançados
- [ ] Exportação PDF
- [ ] API pública
⸻
🤝 Contribuindo

Contribuições são sempre bem-vindas! Veja como você pode ajudar:

Como Contribuir

1. Fork o projeto
2. Clone seu fork
3. Crie uma branch para sua feature (git checkout -b feature/MinhaFeature)
4. Commit suas mudanças (git commit -m 'feat: adiciona MinhaFeature')
5. Push para a branch (git push origin feature/MinhaFeature)
6. Abra um Pull Request

Diretrizes

- Siga os padrões de código do projeto
- Escreva testes para novas funcionalidades
- Atualize a documentação quando necessário
- Use commits semânticos (feat, fix, docs, etc.)
- Seja respeitoso e construtivo nos comentários

Commits Semânticos

feat: nova funcionalidade
fix: correção de bug
docs: documentação
style: formatação, ponto e vírgula, etc
refactor: refatoração de código
test: adição ou modificação de testes
chore: atualização de dependências, build, etc

⸻
📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.
⸻
👥 Equipe

- [Seu Nome] - Full Stack Developer - @seu-usuario
⸻
🙏 Agradecimentos

- Expo - Plataforma incrível para desenvolvimento React Native
- Go - Linguagem poderosa e eficiente
- Firebase - Backend as a Service completo
- React Native - Framework mobile multiplataforma
- Comunidade open source por todas as bibliotecas incríveis
⸻
📞 Contato

- Email: contato@kairos.app
- Website: www.kairos.app
- GitHub: @seu-usuario
- LinkedIn: Seu Nome
⸻
<div align="center">
  <p>⭐ Se este projeto foi útil para você, considere dar uma estrela!</p>
  <p>Feito com ❤️ pela equipe Kairos</p>
  <p>© 2026 Kairos - Todos os direitos reservados</p>
</div>
