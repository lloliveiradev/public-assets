## ☸️ About the Project

AIOps K8s is an AIOps platform for Kubernetes, in a polyglot monorepo. When something goes wrong in a cluster, the system receives the signal, investigates the cause, decides whether it can act and, if so, fixes it and checks that the problem is gone, with every step on record.

The flow starts at an ingestion API (a webhook, Alertmanager or the cluster's own events) and triggers a Temporal workflow. Python and Go workers collect signals from Prometheus and Loki, generate the diagnosis with Gemini, pass the decision through a policy engine with guardrails (and human approval when needed) and run the remediation on the cluster.

> A study and portfolio project, still evolving. The code is in a private repository.

## 🚀 Architecture Overview

Every incident goes through a five-step pipeline:

1. **Detect**: the signal is normalized and the incident is recorded.
2. **Diagnose**: a language model and heuristics infer the cause and suggest an action, using observability tools.
3. **Decide**: policies and guardrails approve, block or ask for human approval.
4. **Remediate**: the approved action is executed, preferably through the tool gateway.
5. **Verify**: health and SLOs are checked after the action. The incident ends as resolved, degraded or blocked by policy.

- **Control Plane (Django)**: multi-tenant API with incidents, approvals, manual actions, policies, an action catalog, SLOs, a knowledge base and topology (CMDB).
- **Web Console (Next.js)**: login, dashboard, incidents, approvals, actions and knowledge, in Portuguese and English.
- **Ingest (FastAPI)**: receives the events and starts the workflow.
- **Tool gateway (FastAPI)**: a single point to query Prometheus, Loki and Kubernetes, with a YAML catalog, rate limiting and a circuit breaker.
- **Operator**: watches the cluster events and feeds the ingest.
- **Workers (Python and Go)**: Python detects, diagnoses and decides; Go remediates and verifies.

- ✅ Everything the agent does is audited: decisions, LLM calls, tool calls and remediations
- ✅ Tools sit behind a gateway, with risk levels and guardrails
- ✅ Policies, the action catalog and SLOs are managed in the Control Plane
- ✅ A local lab with a test cluster, kept apart from the product

## 🛠️ Technologies

### Backend
- [Python](https://www.python.org) - Workers, ingest, gateway and Operator
- [Go](https://go.dev) - Remediation and verification workers
- [Django](https://www.djangoproject.com) and [Django REST Framework](https://www.django-rest-framework.org) - Control Plane
- [FastAPI](https://fastapi.tiangolo.com) - Ingest and tool gateway
- [Temporal](https://temporal.io) - Workflow orchestration
- [Gemini](https://ai.google.dev) - Diagnosis with generative AI

### Frontend
- [Next.js](https://nextjs.org) and [React](https://react.dev) - Web console
- [TypeScript](https://www.typescriptlang.org) - Typing
- [Tailwind CSS](https://tailwindcss.com) and [shadcn/ui](https://ui.shadcn.com) - Interface
- [next-intl](https://next-intl.dev) - Portuguese and English
- [TanStack Query](https://tanstack.com/query) and [TanStack Table](https://tanstack.com/table) - Data and tables

### Data and observability
- [PostgreSQL](https://www.postgresql.org) - Control Plane and Temporal database
- [Redis](https://redis.io) - Shared rate limiting and circuit breaker
- [Prometheus](https://prometheus.io), [Grafana](https://grafana.com) and [Loki](https://grafana.com/oss/loki) - Metrics, dashboards and logs
- [OpenTelemetry](https://opentelemetry.io) and [Jaeger](https://www.jaegertracing.io) - Traces
- [ClickHouse](https://clickhouse.com) - Optional backend for traces, logs and metrics

### Infrastructure
- [Kubernetes](https://kubernetes.io) and [k3s](https://k3s.io) - Lab cluster
- [Docker Compose](https://docs.docker.com/compose) - Local environment
- [Infisical](https://infisical.com) - Secrets management

## 🛠️ Key Features

### 🤖 Incident response
- ✅ Input from webhooks, Alertmanager, Prometheus or cluster events
- ✅ Diagnosis with an LLM and heuristics
- ✅ Decisions with guardrails and optional human approval
- ✅ Automatic remediation and verification

### 🔐 Governance and security
- ✅ Multi-tenant, with JWT authentication
- ✅ Cluster credentials stored encrypted
- ✅ Login attempt limits, a password policy and an audit log
- ✅ Maintenance windows tied to policies

### 🗺️ Context and knowledge
- ✅ Topology of configuration items (CMDB) and their relationships
- ✅ Knowledge base, postmortems and feedback

### 📈 Observability of the platform itself
- ✅ Per-activity metrics (latency, calls, errors and estimated token cost)
- ✅ OpenTelemetry traces and health endpoints

## 🚀 Project Structure

```bash
aiops-k8s/
├── apps/
│   ├── api/          # Control Plane (Django REST)
│   ├── web/          # Web console (Next.js)
│   ├── services/     # Ingest and tool gateway
│   ├── workers/      # Temporal workers in Python and Go
│   └── operator/     # Operator that watches the cluster events
├── packages/
│   ├── aiops-shared/ # Contracts and table names
│   └── config/       # Policies and tool catalog
├── infra/            # Lab cluster and observability
├── docs/             # Contracts, workers, gateway and architecture
└── docker-compose.yaml
```

## 🧪 Local Lab

The whole stack comes up with Docker Compose (`make dev-up`): a k3s cluster, Temporal, Postgres, observability and the workers. Test workloads (a demo API, a load generator and a failure injector) simulate a customer's cluster to validate the flow end to end.

## 📄 License

This project is licensed under the MIT License.
