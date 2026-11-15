## 💳 Sobre el Proyecto

Iris Gate es un gateway de pagos "API-first" hecho para estudio. Reúne en un solo proyecto los problemas clásicos de un sistema de pagos: cobros idempotentes, mensajes que no pueden perderse, análisis de fraude y aislamiento entre clientes.

Un servicio en Go se encarga de comercios, claves de API e intenciones de pago. Un worker en NestJS calcula el riesgo de fraude a partir de los eventos de Kafka. Un panel en Next.js lo muestra todo al comercio. Los contratos OpenAPI y AsyncAPI son el único lenguaje compartido entre las partes.

> Proyecto de estudio y portafolio: se ejecuta solo en un entorno local, usa un adquirente de mentira y nunca recibe número de tarjeta, CVV ni vencimiento (solo un `card_token` opaco).

## 🚀 Visión General de la Arquitectura

- **API de pagos (Go)**: comercios, claves de API y el ciclo de vida del pago.
- **Antifraude (NestJS)**: reglas de riesgo que responden aprobar, revisar o rechazar.
- **Panel del comercio (Next.js)**: pantallas de pagos en portugués, inglés y español.
- **Mensajería (Kafka)**: el estado y el evento se guardan en la misma transacción (outbox) y quien consume evita duplicados (inbox).

- ✅ DDD estratégico, con un contexto delimitado por dominio (identidad, pagos y fraude)
- ✅ Arquitectura hexagonal: `domain → application → infra`
- ✅ Contratos como fuente de la verdad: OpenAPI y AsyncAPI generan los tipos en Go y TypeScript
- ✅ Decisiones síncronas, hechos asíncronos
- ✅ Falla cerrada: ante la duda, el sistema retiene o rechaza, nunca aprueba

## 🛠️ Tecnologías

### Backend
- [Go](https://go.dev) - API de pagos e identidad
- [chi](https://go-chi.io) - Enrutador HTTP
- [pgx](https://github.com/jackc/pgx) - Driver de PostgreSQL
- [NestJS](https://nestjs.com) - Worker del antifraude
- [Prisma](https://www.prisma.io) - ORM del antifraude
- [KafkaJS](https://kafka.js.org) - Cliente Kafka en el worker

### Frontend
- [Next.js](https://nextjs.org) y [React](https://react.dev) - Panel del comercio
- [TypeScript](https://www.typescriptlang.org) - Tipado en todo el código TypeScript
- [Tailwind CSS](https://tailwindcss.com) y [shadcn/ui](https://ui.shadcn.com) - Interfaz
- [next-intl](https://next-intl.dev) - Traducción en tres idiomas
- [TanStack Query](https://tanstack.com/query) y [TanStack Table](https://tanstack.com/table) - Datos y tablas

### Datos y mensajería
- [PostgreSQL](https://www.postgresql.org) - Base de datos
- [Apache Kafka](https://kafka.apache.org) - Eventos (modo KRaft)
- [Karapace](https://github.com/Aiven-Open/karapace) - Registro de schemas
- [OpenAPI](https://www.openapis.org) y [AsyncAPI](https://www.asyncapi.com) - Contratos

### Calidad e infraestructura
- [Docker Compose](https://docs.docker.com/compose) - Entorno local
- [GitHub Actions](https://github.com/features/actions) - Integración continua
- [Jest](https://jestjs.io), [Vitest](https://vitest.dev) y [Playwright](https://playwright.dev) - Pruebas
- [golangci-lint](https://golangci-lint.run), [ESLint](https://eslint.org) y [Prettier](https://prettier.io) - Calidad de código
- [Yarn](https://yarnpkg.com) (workspaces) y [Make](https://www.gnu.org/software/make) - Monorepo y comandos

## 🛠️ Principales Recursos

### 🔐 Identidad
- ✅ Alta de comercios y emisión de claves de API
- ✅ Solo se guarda el hash Argon2id de la clave, y el secreto se muestra una única vez
- ✅ Revocación de claves

### 💰 Pagos
- ✅ Crear, autorizar y capturar intenciones de pago
- ✅ Importes en centavos (enteros) con moneda ISO-4217
- ✅ Idempotencia por clave, para repetir una llamada sin cobrar dos veces
- ✅ Cada comercio solo ve sus propios pagos

### 🛡️ Antifraude
- ✅ Reglas por especificación: tarjeta bloqueada, importe inusual, velocidad y ráfagas de rechazos
- ✅ Decisión de aprobar, revisar o rechazar a partir de una puntuación

### 📊 Panel
- ✅ Página de inicio y pantallas de pagos
- ✅ Portugués, inglés y español
- ✅ Sesión en una cookie `httpOnly`

## 🧭 Próximos Pasos

El proyecto sigue evolucionando, en fases con su propia especificación:

- 🔜 Usuarios, roles y permisos, con aislamiento por tenant en la base de datos
- 🔜 Bóveda de tarjetas de prueba con cifrado en sobre
- 🔜 Checkout alojado, catálogo y enlaces de pago
- 🔜 Webhooks firmados y registro de solicitudes
- 🔜 Observabilidad, pruebas de extremo a extremo y una CI más completa
- 🔜 Despliegue en AWS, con infraestructura como código (Terraform)

## 🚀 Estructura del Proyecto

```bash
iris-gate/
├── apps/
│   ├── api/          # API en Go (identidad y pagos)
│   ├── anti-fraud/   # Worker de antifraude en NestJS
│   └── web/          # Panel del comercio en Next.js
├── libs/
│   ├── identity/     # Comercios y claves de API
│   ├── payments/     # Intenciones de pago, outbox y adquirente
│   ├── fraud/        # Reglas de riesgo en TypeScript
│   ├── contracts/    # OpenAPI, AsyncAPI y tipos generados
│   └── sdk-web/      # Cliente tipado del panel
├── infra/            # Docker Compose: Postgres, Kafka y Karapace
└── docs/             # Diseño, especificaciones, roadmap y ADRs
```

## 🚀 Comenzando

Requisitos previos: Go, Node.js con Corepack y Docker.

```bash
git clone https://github.com/lloliveiradev/iris-gate.git
cd iris-gate
make bootstrap   # instala las dependencias y levanta la infraestructura local
make dev         # API en :8080 y panel en :3000
```

La guía completa, la documentación de arquitectura y el plan de entrega están en el [repositorio](https://github.com/lloliveiradev/iris-gate).

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT.
