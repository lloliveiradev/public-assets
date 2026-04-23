## 📱 Sobre o Projeto

O Kairos é uma solução completa de gerenciamento financeiro pessoal que permite aos usuários controlar suas finanças de forma inteligente e intuitiva. O projeto é composto por:

- 📱 Aplicativo Mobile Multiplataforma (iOS, Android, Web) - React Native + Expo
- 🚀 API REST Backend - Go + Firebase + Cloud Firestore
- 🔐 Sistema de Autenticação Seguro - Firebase Authentication
- 📊 Dashboard de Análise Financeira - Gráficos e relatórios interativos

Na mitologia grega, Kairos representa o momento certo, a oportunidade perfeita. Assim como o conceito mitológico, nosso aplicativo ajuda você a tomar decisões financeiras no momento certo, com as informações certas.

## 🚀 Visão Geral da Arquitetura

O projeto segue uma arquitetura de microserviços com separação clara entre frontend e backend:

```
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
```

- ✅ Clean Architecture no backend (Go)
- ✅ Component-Based no frontend (React Native)
- ✅ RESTful API para comunicação
- ✅ File-based Routing com Expo Router
- ✅ Type Safety com TypeScript e Go
- ✅ Dependency Injection e inversão de controle
- ✅ Repository Pattern para abstração de dados

## 🛠️ Tecnologias

### Frontend
- [React Native](https://reactnative.dev) - Framework mobile
- [Expo](https://expo.dev) - Plataforma de desenvolvimento
- [TypeScript](https://www.typescriptlang.org) - Superset JavaScript
- [Expo Router](https://docs.expo.dev/router) - Roteamento file-based
- [NativeWind](https://www.nativewind.dev) - TailwindCSS para React Native
- [Firebase](https://firebase.google.com) - Backend as a Service
- [React Native Reanimated](https://www.reanimated.org) - Animações nativas
- [Axios](https://axios-http.com) - Cliente HTTP
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Armazenamento local

### Backend
- [Go](https://go.dev) - Linguagem de programação
- [Chi Router](https://go-chi.io) - Router HTTP
- [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) - Autenticação e gerenciamento
- [Cloud Firestore](https://firebase.google.com/docs/firestore) - Banco de dados NoSQL
- [Google Cloud APIs](https://cloud.google.com) - Serviços Google Cloud
- [UUID](https://github.com/google/uuid) - Gerador de IDs únicos
- [godotenv](https://github.com/joho/godotenv) - Variáveis de ambiente

## 🛠️ Principais Recursos

### 🔐 Autenticação & Segurança
- ✅ Login com email e senha
- ✅ Login social (Google, Apple)
- ✅ Recuperação de senha
- ✅ Autenticação JWT com Firebase
- ✅ Persistência de sessão
- ✅ Middleware de autorização

### 💰 Gestão de Transações
- ✅ Cadastro de receitas e despesas
- ✅ Categorização personalizável
- ✅ Filtros avançados (período, categoria, conta)
- ✅ Busca e ordenação
- ✅ Edição e exclusão de transações
- ✅ Histórico completo

### 🏦 Contas Bancárias
- ✅ Múltiplas contas (corrente, poupança, investimento)
- ✅ Suporte aos principais bancos brasileiros
- ✅ Saldo em tempo real
- ✅ Transferências entre contas
- ✅ Categorias personalizadas

### 📊 Relatórios & Analytics
- ✅ Dashboard interativo
- ✅ Gráficos de receitas vs despesas
- ✅ Análise por categoria
- ✅ Comparativos mensais
- ✅ Projeções financeiras
- ✅ Exportação de dados

### 🎯 Metas Financeiras
- ✅ Definição de objetivos
- ✅ Acompanhamento de progresso
- ✅ Notificações de conquistas
- ✅ Planejamento financeiro

### 🎨 Interface & UX
- ✅ Design moderno e intuitivo
- ✅ Tema claro e escuro
- ✅ Animações fluidas
- ✅ Responsivo para todos os dispositivos
- ✅ Suporte a múltiplos idiomas (preparado)

## 🚀 Estrutura do Projeto

```
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
```

## 🚀 Começando

### Pré-requisitos
- [Git](https://git-scm.com) - Controle de versão
- [Node.js](https://nodejs.org) (v18+) - Runtime JavaScript
- [Go](https://go.dev) (v1.24+) - Linguagem do backend
- [Make](https://www.gnu.org/software/make) - Automação de comandos
- [Conta no Firebase](https://firebase.google.com)
- [Expo CLI](https://docs.expo.dev/workflow/expo-cli)
- [Xcode](https://developer.apple.com/xcode) (para iOS) ou [Android Studio](https://developer.android.com/studio) (para Android)

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/kairos.git
cd kairos
```

2. Instale as dependências para cada parte:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
go mod download
```

### Configurar variáveis de ambiente

1. **Configurar o Firebase**:
    - Crie um projeto no Firebase Console.
    - Ative o Authentication (Email/Password, Google, Apple).
    - Ative o Firestore Database.
    - Baixe as credenciais (JSON service account para o backend, Web config para o frontend).

2. **Arquivos de ambiente**:
```bash
# Frontend
cd frontend
cp .env.example .env

# Backend
cd backend
cp .env.example .env
```

### Iniciar os servidores de desenvolvimento

1. **Backend**:
```bash
cd backend
go run cmd/app/main.go
```

2. **Frontend**:
```bash
cd frontend
npx expo start
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor, siga estes passos:

1. Faça um fork do projeto
2. Crie sua branch de feature (`git checkout -b feature/AmazingFeature`)
3. Faça commit das suas alterações (`git commit -m 'feat: add AmazingFeature'`)
4. Faça push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
