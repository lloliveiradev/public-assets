## 📚 Sobre o Projeto

Este projeto é uma proposta de reformulação do website da **SETEC (Serviços Técnicos Gerais)**, uma autarquia da Prefeitura de Campinas, São Paulo. O objetivo é oferecer uma interface moderna, intuitiva e acessível para que os cidadãos possam acessar informações e serviços públicos de forma eficiente.

O projeto consiste em um website estático moderno integrado ao ecossistema Firebase, focado em fornecer informações detalhadas sobre serviços funerários, transparência pública, gestão de publicidade em áreas públicas e acesso a documentos oficiais.

## 🛠️ Tecnologias

### Frontend
- [HTML5](https://html.spec.whatwg.org/) e [CSS3](https://www.w3.org/Style/CSS/) — Estrutura e estilização base
- [Bootstrap 5](https://getbootstrap.com/) — Framework CSS para desenvolvimento responsivo
- [jQuery](https://jquery.com/) — Biblioteca JavaScript para manipulação de DOM
- [FontAwesome](https://fontawesome.com/) — Conjunto de ícones
- [Google Fonts (Roboto)](https://fonts.google.com/specimen/Roboto) — Tipografia

### Backend e Infraestrutura
- [Firebase Hosting](https://firebase.google.com/docs/hosting) — Hospedagem rápida e segura
- [Firebase Firestore](https://firebase.google.com/docs/firestore) — Banco de dados NoSQL em tempo real
- [Firebase Storage](https://firebase.google.com/docs/storage) — Armazenamento de arquivos e documentos
- [Firebase Auth](https://firebase.google.com/docs/auth) — Sistema de autenticação

## 🗂️ Estrutura do Projeto

```bash
setec-site/
├── public/                # Conteúdo principal do site
│   ├── assets/            # Recursos estáticos
│   │   ├── css/           # Folhas de estilo
│   │   ├── docs/          # Documentos oficiais e formulários PDF
│   │   ├── fonts/         # Fontes locais
│   │   ├── images/        # Imagens e logotipos
│   │   └── svg/           # Vetores e ícones SVG
│   ├── pag/               # Sub-páginas temáticas
│   │   ├── funeraria.html     # Serviços funerários e cemitérios
│   │   ├── transparencia.html # Portal da transparência
│   │   ├── publicidade.html   # Publicidade em áreas públicas
│   │   ├── solo.html          # Gestão de uso do solo
│   │   └── covid19.html       # Informações e protocolos
│   ├── vendor/            # Bibliotecas de terceiros
│   └── index.html         # Página inicial
├── firebase.json          # Configurações do Firebase
├── firestore.rules        # Regras de segurança do banco de dados
├── storage.rules          # Regras de segurança do armazenamento
└── README.md              # Documentação do projeto
```

## ✨ Principais Recursos

- **Serviços Funerários** — Informações sobre cemitérios, crematórios e planos
- **Transparência Pública** — Acesso a dados da autarquia e prestação de contas
- **Documentação Online** — Repositório de formulários e requerimentos (exumação, transferência, etc.)
- **Gestão de Publicidade** — Licenciamento de anúncios em áreas públicas e privadas
- **Interface Responsiva** — Design adaptável para qualquer dispositivo

## 🚀 Começando

### Pré-requisitos
- Conta no [Firebase](https://console.firebase.google.com/)
- [Firebase CLI](https://firebase.google.com/docs/cli) instalado globalmente

### Instalação e Deploy

1. Clone o repositório:
```bash
git clone [REPOSITORY_URL]
cd setec-site
```

2. Inicialize o Firebase e visualize localmente:
```bash
firebase login
firebase serve
```

3. Realize o deploy:
```bash
firebase deploy
```

## 📄 Licença

Este projeto é desenvolvido para fins de modernização dos serviços públicos da SETEC Campinas e está licenciado sob a [Licença MIT](LICENSE).
