## 💳 About the Project

Iris Gate is an API-first payments gateway built for study. It brings the classic problems of a payments system together in one project: idempotent charges, messages that must never be lost, fraud analysis and isolation between customers.

A Go service owns merchants, API keys and payment intents. A NestJS worker scores fraud from Kafka events. A Next.js app is the merchant dashboard. The OpenAPI and AsyncAPI contracts are the only shared language between the parts.

> A study and portfolio project: it runs only on a local machine, uses a fake acquirer and never accepts a card number, CVV or expiry (only an opaque `card_token`).

## 🚀 Architecture Overview

- **Payments API (Go)**: merchants, API keys and the payment lifecycle.
- **Anti-fraud (NestJS)**: risk rules that answer approve, review or reject.
- **Merchant dashboard (Next.js)**: payment screens in Portuguese, English and Spanish.
- **Messaging (Kafka)**: state and event are written in the same transaction (outbox) and consumers avoid duplicates (inbox).

- ✅ Strategic DDD, with one bounded context per domain (identity, payments and fraud)
- ✅ Hexagonal architecture: `domain → application → infra`
- ✅ Contracts as the source of truth: OpenAPI and AsyncAPI generate the Go and TypeScript types
- ✅ Synchronous decisions, asynchronous facts
- ✅ Fail closed: when in doubt, the system holds or rejects, never approves

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
