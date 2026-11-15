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
