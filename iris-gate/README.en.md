## 💳 About the Project

Iris Gate is an API-first payments gateway built for study. It brings the classic problems of a payments system together in one project: idempotent charges, messages that must never be lost, fraud analysis and isolation between customers.

A Go service owns merchants, API keys and payment intents. A NestJS worker scores fraud from Kafka events. A Next.js app is the merchant dashboard. The OpenAPI and AsyncAPI contracts are the only shared language between the parts.

> A study and portfolio project: it runs only on a local machine, uses a fake acquirer and never accepts a card number, CVV or expiry (only an opaque `card_token`).

## 🚀 Architecture Overview

- **Payments API (Go)**: merchants, API keys and the payment lifecycle.
- **Anti-fraud (NestJS)**: risk rules that answer approve, review or reject.
- **Merchant dashboard (Next.js)**: payment screens in Portuguese, English and Spanish.
- **Messaging (Kafka)**: state and event are written in the same transaction (outbox) and consumers avoid duplicates (inbox).

✅ Strategic DDD, with one bounded context per domain (identity, payments and fraud)
✅ Hexagonal architecture: `domain → application → infra`
✅ Contracts as the source of truth: OpenAPI and AsyncAPI generate the Go and TypeScript types
✅ Synchronous decisions, asynchronous facts
✅ Fail closed: when in doubt, the system holds or rejects, never approves

## 🛠️ Technologies

### Backend
- [Go](https://go.dev) - Payments and identity API
- [chi](https://go-chi.io) - HTTP router
- [pgx](https://github.com/jackc/pgx) - PostgreSQL driver
- [NestJS](https://nestjs.com) - Anti-fraud worker
- [Prisma](https://www.prisma.io) - Anti-fraud ORM
- [KafkaJS](https://kafka.js.org) - Kafka client in the worker

### Frontend
- [Next.js](https://nextjs.org) and [React](https://react.dev) - Merchant dashboard
- [TypeScript](https://www.typescriptlang.org) - Typing across all TypeScript code
- [Tailwind CSS](https://tailwindcss.com) and [shadcn/ui](https://ui.shadcn.com) - Interface
- [next-intl](https://next-intl.dev) - Three-language translation
- [TanStack Query](https://tanstack.com/query) and [TanStack Table](https://tanstack.com/table) - Data and tables

### Data and messaging
- [PostgreSQL](https://www.postgresql.org) - Database
- [Apache Kafka](https://kafka.apache.org) - Events (KRaft mode)
- [Karapace](https://github.com/Aiven-Open/karapace) - Schema registry
- [OpenAPI](https://www.openapis.org) and [AsyncAPI](https://www.asyncapi.com) - Contracts

### Quality and infrastructure
- [Docker Compose](https://docs.docker.com/compose) - Local environment
- [GitHub Actions](https://github.com/features/actions) - Continuous integration
- [Jest](https://jestjs.io), [Vitest](https://vitest.dev) and [Playwright](https://playwright.dev) - Tests
- [golangci-lint](https://golangci-lint.run), [ESLint](https://eslint.org) and [Prettier](https://prettier.io) - Code quality
- [Yarn](https://yarnpkg.com) (workspaces) and [Make](https://www.gnu.org/software/make) - Monorepo and commands

## 🛠️ Key Features

### 🔐 Identity
- ✅ Merchant sign-up and API key issuing
- ✅ Only the Argon2id hash of a key is stored, and the secret is shown once
- ✅ Key revocation

### 💰 Payments
- ✅ Create, authorize and capture payment intents
- ✅ Amounts in cents (integers) with an ISO-4217 currency
- ✅ Idempotency keys, so a call can be repeated without charging twice
- ✅ Each merchant only sees its own payments

### 🛡️ Anti-fraud
- ✅ Specification-based rules: blocked card, unusual amount, velocity and decline bursts
- ✅ An approve, review or reject decision from a score

### 📊 Dashboard
- ✅ Landing page and payment screens
- ✅ Portuguese, English and Spanish
- ✅ Session in an `httpOnly` cookie

## 🧭 What's Next

The project keeps evolving, in phases with their own specification:

- 🔜 Users, roles and permissions, with tenant isolation in the database
- 🔜 Test-card vault with envelope encryption
- 🔜 Hosted checkout, catalog and payment links
- 🔜 Signed webhooks and a request log
- 🔜 Observability, end-to-end tests and a fuller CI
- 🔜 Deployment on AWS, with infrastructure as code (Terraform)

## 🚀 Project Structure

```bash
iris-gate/
├── apps/
│   ├── api/          # Go API (identity and payments)
│   ├── anti-fraud/   # NestJS anti-fraud worker
│   └── web/          # Next.js merchant dashboard
├── libs/
│   ├── identity/     # Merchants and API keys
│   ├── payments/     # Payment intents, outbox and acquirer
│   ├── fraud/        # Risk rules in TypeScript
│   ├── contracts/    # OpenAPI, AsyncAPI and generated types
│   └── sdk-web/      # Typed dashboard client
├── infra/            # Docker Compose: Postgres, Kafka and Karapace
└── docs/             # Design, specs, roadmap and ADRs
```

## 🚀 Getting Started

Prerequisites: Go, Node.js with Corepack and Docker.

```bash
git clone https://github.com/lloliveiradev/iris-gate.git
cd iris-gate
make bootstrap   # installs dependencies and starts the local infrastructure
make dev         # API on :8080 and dashboard on :3000
```

The full guide, the architecture documentation and the delivery plan are in the [repository](https://github.com/lloliveiradev/iris-gate).

## 📄 License

This project is licensed under the MIT License.
