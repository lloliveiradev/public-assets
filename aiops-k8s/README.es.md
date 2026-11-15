## ☸️ Sobre el Proyecto

AIOps K8s es una plataforma de AIOps para Kubernetes, en un monorepo políglota. Cuando algo sale mal en un clúster, el sistema recibe la señal, investiga la causa, decide si puede actuar y, si puede, lo corrige y comprueba que el problema desapareció, con cada paso registrado.

El flujo empieza en una API de ingesta (un webhook, Alertmanager o los eventos del propio clúster) y dispara un workflow en Temporal. Workers en Python y en Go recolectan señales de Prometheus y de Loki, generan el diagnóstico con Gemini, pasan la decisión por un motor de políticas con guardrails (y aprobación humana cuando hace falta) y ejecutan la remediación en el clúster.

> Proyecto de estudio y portafolio, todavía en evolución. El código está en un repositorio privado.

## 🚀 Visión General de la Arquitectura

Cada incidente recorre un pipeline de cinco etapas:

1. **Detectar**: la señal se normaliza y el incidente se registra.
2. **Diagnosticar**: un modelo de lenguaje y heurísticas infieren la causa y sugieren una acción, usando herramientas de observabilidad.
3. **Decidir**: las políticas y los guardrails aprueban, bloquean o piden aprobación humana.
4. **Remediar**: la acción aprobada se ejecuta, preferentemente por el gateway de herramientas.
5. **Verificar**: la salud y los SLOs se comprueban después de la acción. El incidente termina como resuelto, degradado o bloqueado por política.

- **Control Plane (Django)**: API multi-tenant con incidentes, aprobaciones, acciones manuales, políticas, catálogo de acciones, SLOs, base de conocimiento y topología (CMDB).
- **Consola Web (Next.js)**: inicio de sesión, panel, incidentes, aprobaciones, acciones y conocimiento, en portugués e inglés.
- **Ingesta (FastAPI)**: recibe los eventos e inicia el workflow.
- **Gateway de herramientas (FastAPI)**: punto único para consultar Prometheus, Loki y Kubernetes, con catálogo en YAML, límite de tasa y circuit breaker.
- **Operator**: observa los eventos del clúster y alimenta la ingesta.
- **Workers (Python y Go)**: Python detecta, diagnostica y decide; Go remedia y verifica.

- ✅ Todo lo que hace el agente queda auditado: decisiones, llamadas al LLM, llamadas a herramientas y remediaciones
- ✅ Herramientas detrás de un gateway, con niveles de riesgo y guardrails
- ✅ Políticas, catálogo de acciones y SLOs gestionados en el Control Plane
- ✅ Laboratorio local con un clúster de prueba, separado del producto

## 🛠️ Tecnologías

### Backend
- [Python](https://www.python.org) - Workers, ingesta, gateway y Operator
- [Go](https://go.dev) - Workers de remediación y verificación
- [Django](https://www.djangoproject.com) y [Django REST Framework](https://www.django-rest-framework.org) - Control Plane
- [FastAPI](https://fastapi.tiangolo.com) - Ingesta y gateway de herramientas
- [Temporal](https://temporal.io) - Orquestación de workflows
- [Gemini](https://ai.google.dev) - Diagnóstico con IA generativa

### Frontend
- [Next.js](https://nextjs.org) y [React](https://react.dev) - Consola web
- [TypeScript](https://www.typescriptlang.org) - Tipado
- [Tailwind CSS](https://tailwindcss.com) y [shadcn/ui](https://ui.shadcn.com) - Interfaz
- [next-intl](https://next-intl.dev) - Portugués e inglés
- [TanStack Query](https://tanstack.com/query) y [TanStack Table](https://tanstack.com/table) - Datos y tablas

### Datos y observabilidad
- [PostgreSQL](https://www.postgresql.org) - Base del Control Plane y de Temporal
- [Redis](https://redis.io) - Límite de tasa y circuit breaker compartidos
- [Prometheus](https://prometheus.io), [Grafana](https://grafana.com) y [Loki](https://grafana.com/oss/loki) - Métricas, paneles y logs
- [OpenTelemetry](https://opentelemetry.io) y [Jaeger](https://www.jaegertracing.io) - Trazas
- [ClickHouse](https://clickhouse.com) - Backend opcional para trazas, logs y métricas

### Infraestructura
- [Kubernetes](https://kubernetes.io) y [k3s](https://k3s.io) - Clúster del laboratorio
- [Docker Compose](https://docs.docker.com/compose) - Entorno local
- [Infisical](https://infisical.com) - Gestión de secretos

## 🛠️ Principales Recursos

### 🤖 Respuesta a incidentes
- ✅ Entrada por webhook, Alertmanager, Prometheus o eventos del clúster
- ✅ Diagnóstico con LLM y heurísticas
- ✅ Decisión con guardrails y aprobación humana opcional
- ✅ Remediación y verificación automáticas

### 🔐 Gobernanza y seguridad
- ✅ Multi-tenant con autenticación JWT
- ✅ Credenciales de clúster guardadas cifradas
- ✅ Límite de intentos de inicio de sesión, política de contraseñas y registro de auditoría
- ✅ Ventanas de mantenimiento asociadas a las políticas

### 🗺️ Contexto y conocimiento
- ✅ Topología de los elementos de configuración (CMDB) y sus relaciones
- ✅ Base de conocimiento, postmortems y feedback

### 📈 Observabilidad de la propia plataforma
- ✅ Métricas por actividad (latencia, llamadas, errores y costo estimado de tokens)
- ✅ Trazas con OpenTelemetry y endpoints de salud

## 🚀 Estructura del Proyecto

```bash
aiops-k8s/
├── apps/
│   ├── api/          # Control Plane (Django REST)
│   ├── web/          # Consola web (Next.js)
│   ├── services/     # Ingesta y gateway de herramientas
│   ├── workers/      # Workers de Temporal en Python y Go
│   └── operator/     # Operator que observa los eventos del clúster
├── packages/
│   ├── aiops-shared/ # Contratos y nombres de tablas
│   └── config/       # Políticas y catálogo de herramientas
├── infra/            # Clúster del laboratorio y observabilidad
├── docs/             # Contratos, workers, gateway y arquitectura
└── docker-compose.yaml
```

## 🧪 Laboratorio Local

Todo el stack levanta con Docker Compose (`make dev-up`): un clúster k3s, Temporal, Postgres, la observabilidad y los workers. Cargas de prueba (una API de demostración, un generador de carga y un inyector de fallas) simulan el clúster de un cliente para validar el flujo de punta a punta.

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT.
