## ☸️ Sobre o Projeto

O AIOps K8s é uma plataforma de AIOps para Kubernetes, em um monorepo poliglota. Quando algo dá errado em um cluster, o sistema recebe o sinal, investiga a causa, decide se pode agir e, se puder, corrige e confere se o problema acabou, tudo com registro de cada passo.

O fluxo começa em uma API de ingestão (webhook, Alertmanager ou eventos do próprio cluster) e dispara um workflow no Temporal. Workers em Python e em Go coletam sinais do Prometheus e do Loki, geram o diagnóstico com o Gemini, passam a decisão por um motor de políticas com guardrails (e aprovação humana quando necessário) e executam a remediação no cluster.

> Projeto de estudo e portfólio, ainda em evolução. O código está em um repositório privado.

## 🚀 Visão Geral da Arquitetura

Cada incidente percorre um pipeline de cinco etapas:

1. **Detectar**: o sinal é normalizado e o incidente registrado.
2. **Diagnosticar**: um modelo de linguagem e heurísticas inferem a causa e sugerem uma ação, usando ferramentas de observabilidade.
3. **Decidir**: as políticas e os guardrails aprovam, bloqueiam ou pedem aprovação humana.
4. **Remediar**: a ação aprovada é executada, preferencialmente pelo gateway de ferramentas.
5. **Verificar**: a saúde e os SLOs são conferidos depois da ação. O incidente termina como resolvido, degradado ou bloqueado por política.

- **Control Plane (Django)**: API multi-tenant com incidentes, aprovações, ações manuais, políticas, catálogo de ações, SLOs, base de conhecimento e topologia (CMDB).
- **Console Web (Next.js)**: login, painel, incidentes, aprovações, ações e conhecimento, em português e inglês.
- **Ingestão (FastAPI)**: recebe os eventos e inicia o workflow.
- **Gateway de ferramentas (FastAPI)**: ponto único para consultar o Prometheus, o Loki e o Kubernetes, com catálogo em YAML, limite de taxa e circuit breaker.
- **Operator**: observa os eventos do cluster e alimenta a ingestão.
- **Workers (Python e Go)**: Python detecta, diagnostica e decide; Go remedia e verifica.

- ✅ Tudo que o agente faz fica auditado: decisões, chamadas ao LLM, chamadas de ferramentas e remediações
- ✅ Ferramentas atrás de um gateway, com níveis de risco e guardrails
- ✅ Políticas, catálogo de ações e SLOs gerenciados no Control Plane
- ✅ Laboratório local com um cluster de teste, separado do produto

## 🛠️ Tecnologias

### Backend
- [Python](https://www.python.org) - Workers, ingestão, gateway e Operator
- [Go](https://go.dev) - Workers de remediação e verificação
- [Django](https://www.djangoproject.com) e [Django REST Framework](https://www.django-rest-framework.org) - Control Plane
- [FastAPI](https://fastapi.tiangolo.com) - Ingestão e gateway de ferramentas
- [Temporal](https://temporal.io) - Orquestração dos workflows
- [Gemini](https://ai.google.dev) - Diagnóstico com IA generativa

### Frontend
- [Next.js](https://nextjs.org) e [React](https://react.dev) - Console web
- [TypeScript](https://www.typescriptlang.org) - Tipagem
- [Tailwind CSS](https://tailwindcss.com) e [shadcn/ui](https://ui.shadcn.com) - Interface
- [next-intl](https://next-intl.dev) - Português e inglês
- [TanStack Query](https://tanstack.com/query) e [TanStack Table](https://tanstack.com/table) - Dados e tabelas

### Dados e observabilidade
- [PostgreSQL](https://www.postgresql.org) - Banco do Control Plane e do Temporal
- [Redis](https://redis.io) - Limite de taxa e circuit breaker compartilhados
- [Prometheus](https://prometheus.io), [Grafana](https://grafana.com) e [Loki](https://grafana.com/oss/loki) - Métricas, painéis e logs
- [OpenTelemetry](https://opentelemetry.io) e [Jaeger](https://www.jaegertracing.io) - Traces
- [ClickHouse](https://clickhouse.com) - Backend opcional para traces, logs e métricas

### Infraestrutura
- [Kubernetes](https://kubernetes.io) e [k3s](https://k3s.io) - Cluster do laboratório
- [Docker Compose](https://docs.docker.com/compose) - Ambiente local
- [Infisical](https://infisical.com) - Gestão de segredos

## 🛠️ Principais Recursos

### 🤖 Resposta a incidentes
- ✅ Entrada por webhook, Alertmanager, Prometheus ou eventos do cluster
- ✅ Diagnóstico com LLM e heurísticas
- ✅ Decisão com guardrails e aprovação humana opcional
- ✅ Remediação e verificação automáticas

### 🔐 Governança e segurança
- ✅ Multi-tenant com autenticação JWT
- ✅ Credenciais de cluster guardadas de forma criptografada
- ✅ Limite de tentativas de login, política de senha e log de auditoria
- ✅ Janelas de manutenção associadas às políticas

### 🗺️ Contexto e conhecimento
- ✅ Topologia dos itens de configuração (CMDB) e seus relacionamentos
- ✅ Base de conhecimento, pós-mortems e feedback

### 📈 Observabilidade da própria plataforma
- ✅ Métricas por atividade (latência, chamadas, erros e custo estimado de tokens)
- ✅ Traces com OpenTelemetry e endpoints de saúde

## 🚀 Estrutura do Projeto

```bash
aiops-k8s/
├── apps/
│   ├── api/          # Control Plane (Django REST)
│   ├── web/          # Console web (Next.js)
│   ├── services/     # Ingestão e gateway de ferramentas
│   ├── workers/      # Workers Temporal em Python e Go
│   └── operator/     # Operator que observa os eventos do cluster
├── packages/
│   ├── aiops-shared/ # Contratos e nomes de tabelas
│   └── config/       # Políticas e catálogo de ferramentas
├── infra/            # Cluster do laboratório e observabilidade
├── docs/             # Contratos, workers, gateway e arquitetura
└── docker-compose.yaml
```

## 🧪 Laboratório Local

A stack inteira sobe com Docker Compose (`make dev-up`): um cluster k3s, o Temporal, o Postgres, a observabilidade e os workers. Cargas de teste (API de demonstração, gerador de carga e injetor de falhas) simulam o cluster de um cliente para validar o fluxo de ponta a ponta.

## 📄 Licença

Este projeto está licenciado sob a Licença MIT.
