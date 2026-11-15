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
