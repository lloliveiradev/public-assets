## 🌐 Sobre o Projeto

O Portfolio Dev é o meu portfólio profissional, o site que você está vendo agora. Ele apresenta projetos, experiências, cursos, tecnologias e idiomas, e tudo é trilíngue: o site inteiro, textos e conteúdo, aparece em português, inglês ou espanhol a partir de uma única fonte de dados.

O conteúdo não está escrito nos componentes. Ele fica no banco de dados e é atualizado por scripts, então trocar um texto ou incluir um projeto não exige mexer no código das telas.

Site no ar: [lloliveira.dev](https://lloliveira.dev)

## 🚀 Visão Geral da Arquitetura

- **Renderização no servidor primeiro**: cada página busca e traduz os dados no servidor e entrega ao navegador apenas texto simples.
- **Ações do servidor como única porta de dados**: não existem rotas de API, e o acesso ao banco nunca chega ao navegador.
- **Tradução em três camadas**: textos da interface, conteúdo do banco e seções estruturadas do currículo.
- **Conteúdo versionado em scripts**: cada script carrega os três idiomas e pode ser executado de novo sem efeitos colaterais.

- ✅ Idioma na rota (`/pt`, `/en`, `/es`), sem páginas duplicadas
- ✅ Conteúdo localizado guardado como JSON `{ pt, en, es }` e reduzido a texto antes de chegar à tela
- ✅ Tema claro e escuro, com a mesma paleta de cores nos dois
- ✅ Imagens e README dos projetos vêm de um repositório de arquivos próprio

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
