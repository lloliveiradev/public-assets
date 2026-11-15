## 💳 Sobre o Projeto

O Iris Gate é um gateway de pagamentos "API-first" feito para estudo. Ele reúne em um só projeto os problemas clássicos de um sistema de pagamentos: cobranças idempotentes, mensagens que não podem se perder, análise de fraude e isolamento entre clientes.

Um serviço em Go cuida de lojistas, chaves de API e intenções de pagamento. Um worker em NestJS calcula o risco de fraude a partir dos eventos do Kafka. Um painel em Next.js mostra tudo para o lojista. Os contratos OpenAPI e AsyncAPI são a única linguagem compartilhada entre as partes.

> Projeto de estudo e portfólio: roda só em ambiente local, usa um adquirente de mentira e nunca recebe número de cartão, CVV ou validade (apenas um `card_token` opaco).

## 🚀 Visão Geral da Arquitetura

- **API de pagamentos (Go)**: lojistas, chaves de API e o ciclo de vida do pagamento.
- **Antifraude (NestJS)**: regras de risco que devolvem aprovar, revisar ou rejeitar.
- **Painel do lojista (Next.js)**: telas de pagamentos em português, inglês e espanhol.
- **Mensageria (Kafka)**: o estado e o evento são gravados na mesma transação (outbox) e quem consome evita duplicidade (inbox).

- ✅ DDD estratégico, com um contexto delimitado por domínio (identidade, pagamentos e fraude)
- ✅ Arquitetura hexagonal: `domain → application → infra`
- ✅ Contratos como fonte da verdade: OpenAPI e AsyncAPI geram os tipos em Go e TypeScript
- ✅ Decisões síncronas, fatos assíncronos
- ✅ Falha fechada: na dúvida, o sistema segura ou rejeita, nunca aprova

## 🛠️ Principais Recursos

### 🔐 Identidade
- ✅ Cadastro de lojistas e emissão de chaves de API
- ✅ Só o hash Argon2id da chave é armazenado, e o segredo aparece uma única vez
- ✅ Revogação de chaves

### 💰 Pagamentos
- ✅ Criar, autorizar e capturar intenções de pagamento
- ✅ Valores em centavos (inteiros) com moeda ISO-4217
- ✅ Idempotência por chave, para repetir uma chamada sem cobrar duas vezes
- ✅ Cada lojista só enxerga os próprios pagamentos

### 🛡️ Antifraude
- ✅ Regras por especificação: cartão bloqueado, valor incomum, velocidade e rajada de recusas
- ✅ Decisão de aprovar, revisar ou rejeitar a partir de uma pontuação

### 📊 Painel
- ✅ Página inicial e telas de pagamentos
- ✅ Português, inglês e espanhol
- ✅ Sessão em cookie `httpOnly`

## 🧭 Próximos Passos

O projeto continua em evolução, em fases com especificação própria:

- 🔜 Usuários, papéis e permissões, com isolamento por tenant no banco
- 🔜 Cofre de cartões de teste com criptografia em envelope
- 🔜 Checkout hospedado, catálogo e links de pagamento
- 🔜 Webhooks assinados e log de requisições
- 🔜 Observabilidade, testes ponta a ponta e CI mais completa
- 🔜 Publicação na AWS, com infraestrutura como código (Terraform)
