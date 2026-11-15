## 📱 Sobre o Projeto

O Solon é um aplicativo de notas inteligentes que combina o poder da IA com uma interface móvel moderna. O aplicativo oferece uma experiência intuitiva para criar, organizar e gerenciar notas, com recursos avançados como reconhecimento de voz, processamento de texto baseado em IA e sincronização em nuvem.

## 🚀 Visão Geral da Arquitetura

O projeto é estruturado em três partes principais:

### Frontend (Mobile)
- Desenvolvido com React Native e Expo
- Interface moderna com TailwindCSS
- Abordagem offline-first com AsyncStorage
- Reconhecimento e transcrição de voz
- Processamento de texto baseado em IA

### Backend (API)
- Framework NestJS
- Integração com Firebase para autenticação e banco de dados
- Serviços do Google Cloud para recursos de IA
- Arquitetura de API RESTful

### Core (Compartilhado)
- Tipos e interfaces compartilhados
- Utilitários e constantes comuns
- Lógica de negócios multiplataforma

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
