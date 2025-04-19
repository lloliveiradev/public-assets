Solon é um aplicativo de notas inteligentes que combina o poder da IA com uma interface móvel moderna. O aplicativo oferece uma experiência intuitiva para criar, organizar e gerenciar notas, com recursos avançados como reconhecimento de voz, processamento de texto com IA e sincronização em nuvem.

## 🚀 Visão Geral da Arquitetura

O projeto é estruturado em três partes principais:

### Frontend (Mobile)
- Desenvolvido com React Native e Expo
- Interface moderna com TailwindCSS
- Abordagem offline-first com AsyncStorage
- Reconhecimento e transcrição de voz
- Processamento de texto com IA

### Backend (API)
- Framework NestJS
- Integração com Firebase para autenticação e banco de dados
- Serviços do Google Cloud para recursos de IA
- Arquitetura RESTful API

### Core (Compartilhado)
- Tipos e interfaces compartilhados
- Utilitários e constantes comuns
- Lógica de negócios multiplataforma

## 🛠️ Tecnologias

### Frontend
- [Expo](https://expo.dev) - Plataforma para desenvolvimento de apps React Native
- [React Native](https://reactnative.dev) - Framework de desenvolvimento móvel
- [TypeScript](https://www.typescriptlang.org) - Linguagem de programação tipada
- [TailwindCSS](https://tailwindcss.com) - Framework CSS para estilização
- [React Navigation](https://reactnavigation.org) - Navegação entre telas
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage) - Armazenamento local
- [React Native Voice](https://github.com/react-native-voice/voice) - Reconhecimento de voz
- [Expo Router](https://docs.expo.dev/router/introduction) - Roteamento baseado em arquivos

### Backend
- [NestJS](https://nestjs.com) - Framework Node.js
- [TypeScript](https://www.typescriptlang.org) - Linguagem de programação tipada
- [Firebase](https://firebase.google.com) - Plataforma de desenvolvimento
  - [Firestore](https://firebase.google.com/docs/firestore) - Banco de dados NoSQL
  - [Firebase Auth](https://firebase.google.com/docs/auth) - Autenticação de usuários
- [Google Cloud](https://cloud.google.com) - Serviços em nuvem
  - [Google Speech-to-Text](https://cloud.google.com/speech-to-text) - API de transcrição de áudio
  - [Google Generative AI](https://cloud.google.com/vertex-ai/generative-ai) - Modelo Gemini 1.5 Flash
- [Jest](https://jestjs.io) - Framework de testes

### Core
- [TypeScript](https://www.typescriptlang.org) - Tipos e interfaces compartilhados
- [Jest](https://jestjs.io) - Utilitários de teste

## 🛠️ Principais Recursos

### 📝 Edição de Notas
- Suporte a reconhecimento de voz
- Tags e marcadores para buscas precisas
- Sincronização em tempo real

### 🗂️ Organização Inteligente
- **Resumo**: Gera resumos concisos mantendo as ideias principais
- **Correção de Texto**: Corrige automaticamente erros gramaticais e ortográficos
- **Extração de Tópicos**: Identifica e extrai os principais tópicos das notas
- **Formalização de Texto**: Transforma o texto para um tom mais formal quando necessário

## 📋 Mapeamento de Telas

### Autenticação
- Autenticação segura com Firebase Auth
- Login com email e senha
- Processo de registro simples

### Recursos Principais
- Dashboard com notas recentes
- Funcionalidade de busca inteligente
- Arquivo para organizar notas
- Perfil do usuário e configurações

## 🚀 Estrutura do Projeto

```
solon/
├── frontend/         # Aplicativo móvel
│   ├── app/         # Rotas e páginas principais
│   ├── components/  # Componentes reutilizáveis
│   ├── assets/      # Recursos estáticos
│   ├── context/     # Contextos React
│   ├── utils/       # Funções utilitárias
│   ├── constants/   # Constantes e configurações
│   └── functions/   # Funções de negócios
│
├── backend/         # Servidor API
│   ├── src/
│   │   ├── annotations/  # Módulo de notas
│   │   ├── auth/        # Autenticação
│   │   ├── config/      # Configurações globais
│   │   ├── firebase/    # Integração Firebase
│   │   ├── gemini/      # Processamento de IA
│   │   ├── roles/       # Gerenciamento de funções
│   │   ├── transcription/ # Serviços de voz
│   │   └── users/       # Gerenciamento de usuários
│
└── core/           # Código compartilhado
    └── src/        # Tipos e utilitários compartilhados
```

## 🚀 Começando

### Pré-requisitos
- Node.js (versão 18 ou superior)
- npm ou yarn
- Expo CLI
- Conta Firebase
- Conta Google Cloud
- Emulador Android/iOS ou dispositivo físico

### Instalação

1. Clone o repositório:
```bash
git clone [URL_DO_REPOSITÓRIO]
cd solon
```

2. Instale as dependências para cada parte:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
npm install

# Core
cd ../core
npm install
```

3. Configure as variáveis de ambiente:
```bash
# Backend .env
APP_CREDENTIALS='{credenciais-google-cloud}'
API_KEY='sua-chave-api'
PROJECT_ID='seu-id-de-projeto'
PROJECT_LOCATION='sua-localização'
FB_CREDENTIALS='{credenciais-firebase}'
FB_API_KEY='sua-chave-api-firebase'
```

4. Inicie os servidores de desenvolvimento:
```bash
# Backend
cd backend
npm run start:dev

# Frontend
cd frontend
npm start
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor, siga estes passos:

1. Faça um fork do projeto
2. Crie sua branch de feature (`git checkout -b feature/FeatureIncrivel`)
3. Faça commit das suas alterações (`git commit -m 'Adiciona uma FeatureIncrivel'`)
4. Faça push para a branch (`git push origin feature/FeatureIncrivel`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.