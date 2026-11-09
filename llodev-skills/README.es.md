# llodev/skills

> Colección de [Agent Skills](https://agentskills.io) creadas por [@lloliveiradev](https://github.com/lloliveiradev) para Claude Code, Cursor, Codex, Windsurf y cualquier agente que hable la spec abierta de Skills. Las skills son paquetes de instrucciones y scripts que extienden las capacidades de los agentes en workflows de desarrollo, documentación, planificación y profesionales.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../../LICENSE)
[![Node.js >= 20](https://img.shields.io/badge/node-%3E%3D20-43853d?logo=node.js&logoColor=white)](https://nodejs.org)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-FE5196?logo=conventionalcommits&logoColor=white)](https://www.conventionalcommits.org)
[![Agent Skills spec](https://img.shields.io/badge/Agent_Skills-spec-7c5cff)](https://agentskills.io)

Cada skill de este repositorio se distribuye como **paquete npm**, **plugin de Claude Code** y **entrada `skills add` de Vercel**. Elige el canal que hable tu agente — las skills son idénticas en los tres.

## Instalación

Elige el canal que encaje con tu agente.

**Claude Code (o cualquier agente que soporte el marketplace):**

```bash
/plugin marketplace add llodev/skills
/plugin install pm-tasks-core pm-tasks-trello pm-tasks-asana
```

**npm (skillpm, skills-npm o bundling en `node_modules`):**

```bash
npm i @llodev/pm-tasks    # meta — instala toda la familia vía peerDeps
```

**Vercel `skills add`:**

```bash
npx skills add llodev/skills/skills/pm-tasks-trello
```

Consulta la [guía de publicación](../../docs/publishing-guide.md) para ver cómo se conectan los tres canales.

## Catálogo

### `pm-tasks-*` — adaptadores de Project Management

Convierten planes de implementación en tareas de PM y las operan vía paste, MCP publish o write-through autónomo. Hay cinco paquetes publicados — el `pm-tasks-core` compartido más los adaptadores de Trello, Asana, Jira y Linear. Además `@llodev/pm-tasks-testkit` — fakes en memoria para los 7 verbos base, para probar skills personalizadas.

**Runtime headless (subpath `/adapter`):** importa `createAdapter` desde cualquier adaptador publicado para ejecutar los verbos canónicos desde tus propios scripts/agents, sin invocar la skill:

```ts
import { createAdapter } from "@llodev/pm-tasks-trello/adapter";

const adapter = await createAdapter({ configPath: ".trello.json", mcp });
const r = await adapter.taskMove({ taskId: "card-1", targetListOrSectionId: "wip-list" });
if (!r.ok) throw new Error(`task.move falló: ${r.code}`);
```

`mcp: (toolName, args) => Promise<unknown>` es un callback proporcionado por el llamador que hace proxy a las tools `mcp__*` del runtime del agent. Misma forma para `@llodev/pm-tasks-asana/adapter`. Contrato completo en [publishing-guide § 11 — Headless runtime](../../docs/publishing-guide.md#11-headless-runtime-pm-tasks-v19) y en los SKILL.md por adapter.

| Paquete                     | Estado    | Fuente                                                         | npm                                 | Vercel CLI                                            |
| --------------------------- | --------- | -------------------------------------------------------------- | ----------------------------------- | ----------------------------------------------------- |
| `@llodev/pm-tasks` _(meta)_ | ✅ v3.1.1  | [packages/pm-tasks/](../../packages/pm-tasks/)                 | `npm i @llodev/pm-tasks`            | —                                                     |
| `@llodev/pm-tasks-core`     | ✅ v1.16.0 | [skills/pm-tasks-core/](../../skills/pm-tasks-core/)           | `npm i @llodev/pm-tasks-core`       | `npx skills add llodev/skills/skills/pm-tasks-core`   |
| `@llodev/pm-tasks-asana`    | ✅ v1.11.0 | [skills/pm-tasks-asana/](../../skills/pm-tasks-asana/)         | `npm i @llodev/pm-tasks-asana`      | `npx skills add llodev/skills/skills/pm-tasks-asana`  |
| `@llodev/pm-tasks-trello`   | ✅ v1.11.0 | [skills/pm-tasks-trello/](../../skills/pm-tasks-trello/)       | `npm i @llodev/pm-tasks-trello`     | `npx skills add llodev/skills/skills/pm-tasks-trello` |
| `@llodev/pm-tasks-testkit`  | ✅ v0.2.0  | [packages/pm-tasks-testkit/](../../packages/pm-tasks-testkit/) | `npm i -D @llodev/pm-tasks-testkit` | —                                                     |
| `@llodev/pm-tasks-jira`     | ✅ v1.3.0  | [skills/pm-tasks-jira/](../../skills/pm-tasks-jira/)           | `npm i @llodev/pm-tasks-jira`       | `npx skills add llodev/skills/skills/pm-tasks-jira`   |
| `@llodev/pm-tasks-linear`   | ✅ v1.2.0  | [skills/pm-tasks-linear/](../../skills/pm-tasks-linear/)       | `npm i @llodev/pm-tasks-linear`     | `npx skills add llodev/skills/skills/pm-tasks-linear` |

> [!NOTE]
> `@llodev/pm-tasks` (meta) se versiona de forma independiente de la familia mediante `onlyUpdatePeerDependentsWhenOutOfRange`. La familia está en `v1.x`; el meta saltó a `v3.0.0` antes del desacoplamiento (actualmente `v3.1.1`).

**Cobertura de verbos.** El vocabulario canónico son 7 verbos base más 3 opcionales; cada adaptador declara lo que soporta en `manifest.json`, y el runtime devuelve `UNSUPPORTED_VERB` para lo que quede fuera. Los adaptadores también pueden declarar verbos personalizados con namespace.

| Adaptador  | 7 base | `task.parent.set` | `task.estimate.set` | `task.sprint.set` | Personalizado                              |
| ---------- | ------ | ----------------- | ------------------- | ----------------- | ------------------------------------------ |
| **linear** | ✅      | ✅                 | ✅                   | ✅                 | —                                          |
| **jira**   | ✅      | ✅                 | ✅                   | —                 | —                                          |
| **trello** | ✅      | —                 | —                   | —                 | `trello.task.batch-create-with-checklists` |
| **asana**  | ✅      | —                 | —                   | —                 | —                                          |

### `@llodev/ts-ddd` — skills de diseño DDD para TypeScript

Skills puras de **conocimiento** para construir un codebase TypeScript + DDD — sin MCP, sin config, sin init. Se activan por el prompt e inyectan decisiones expertas (validación basada en `Result`, transiciones de estado vía `cloneWith`, closed sets basados en enum, pares de adaptador Firestore/InMemory) para cada capa arquitectónica, más una compañera CQRS de lectura.

| Paquete                         | Estado   | Fuente                                                               | npm                                   | Vercel CLI                                                  |
| ------------------------------- | -------- | -------------------------------------------------------------------- | ------------------------------------- | ----------------------------------------------------------- |
| `@llodev/ts-ddd` _(meta)_       | ✅ v0.1.0 | [packages/ts-ddd/](../../packages/ts-ddd/)                           | `npm i @llodev/ts-ddd`                | —                                                           |
| `@llodev/ts-ddd-entity`         | ✅ v0.1.0 | [skills/ts-ddd-entity/](../../skills/ts-ddd-entity/)                 | `npm i @llodev/ts-ddd-entity`         | `npx skills add llodev/skills/skills/ts-ddd-entity`         |
| `@llodev/ts-ddd-value-object`   | ✅ v0.1.0 | [skills/ts-ddd-value-object/](../../skills/ts-ddd-value-object/)     | `npm i @llodev/ts-ddd-value-object`   | `npx skills add llodev/skills/skills/ts-ddd-value-object`   |
| `@llodev/ts-ddd-dto`            | ✅ v0.1.0 | [skills/ts-ddd-dto/](../../skills/ts-ddd-dto/)                       | `npm i @llodev/ts-ddd-dto`            | `npx skills add llodev/skills/skills/ts-ddd-dto`            |
| `@llodev/ts-ddd-use-case`       | ✅ v0.1.0 | [skills/ts-ddd-use-case/](../../skills/ts-ddd-use-case/)             | `npm i @llodev/ts-ddd-use-case`       | `npx skills add llodev/skills/skills/ts-ddd-use-case`       |
| `@llodev/ts-ddd-repository`     | ✅ v0.1.0 | [skills/ts-ddd-repository/](../../skills/ts-ddd-repository/)         | `npm i @llodev/ts-ddd-repository`     | `npx skills add llodev/skills/skills/ts-ddd-repository`     |
| `@llodev/ts-ddd-controller`     | ✅ v0.1.0 | [skills/ts-ddd-controller/](../../skills/ts-ddd-controller/)         | `npm i @llodev/ts-ddd-controller`     | `npx skills add llodev/skills/skills/ts-ddd-controller`     |
| `@llodev/ts-ddd-domain-service` | ✅ v0.1.0 | [skills/ts-ddd-domain-service/](../../skills/ts-ddd-domain-service/) | `npm i @llodev/ts-ddd-domain-service` | `npx skills add llodev/skills/skills/ts-ddd-domain-service` |
| `@llodev/ts-query-cqrs`         | ✅ v0.1.0 | [skills/ts-query-cqrs/](../../skills/ts-query-cqrs/)                 | `npm i @llodev/ts-query-cqrs`         | `npx skills add llodev/skills/skills/ts-query-cqrs`         |

> [!NOTE]
> `ts-query-cqrs` es la compañera del lado de lectura — cubre `*Query` ports y read use cases `find-*` que se mantienen separados del par de escritura `ts-ddd-repository`/`ts-ddd-use-case`. Instala `@llodev/ts-ddd` para traer las 8 skills de una vez.

## Compatibilidad de agentes

Cada skill publicada declara qué agentes soporta en el campo `compatibility.agents` de su frontmatter. La matriz actual:

> **Claude Code** · **Cursor** · **Codex** · **Windsurf** · **Cline** · **Roo Code** (Gemini CLI parcial vía capa de traducción)

## Layout del repositorio

Las skills viven planas bajo `skills/` (un directorio por skill, la convención
que esperan los indexadores de skills); la pertenencia a la familia se indica con
el prefijo `pm-tasks-` en el nombre y el campo `metadata.family` de cada skill, no
con el anidamiento de directorios. Los paquetes que no son skills (meta-paquete,
testkit) viven bajo `packages/`.

```
.
├── skills/                    Todas las skills — planas, un directorio cada una
│   ├── pm-tasks-core/         Extracción compartida + vocabulario CRUD (family: pm-tasks)
│   ├── pm-tasks-asana/        Adaptador Asana (parent + subtasks, custom fields, sections)
│   ├── pm-tasks-trello/       Adaptador Trello (boards, lists, labels, members)
│   ├── pm-tasks-jira/         Adaptador Jira (epics, estimaciones, transiciones)
│   ├── pm-tasks-linear/       Adaptador Linear (cycles, labels, campos temporales nativos)
│   ├── django-schema-design/  Diseño de esquema: estrategia de PK, índices, constraints, migraciones
│   ├── ts-ddd-entity/         Entidades de dominio: Entity base, Result.combine, transiciones cloneWith
│   ├── ts-ddd-value-object/   Value objects: VOs closed-set + compuestos, tryCreate/create
│   ├── ts-ddd-dto/            DTOs & contracts: schemas Zod 4, tipos z.infer, enums closed-set
│   ├── ts-ddd-use-case/       Use cases de aplicación: UseCase<IN,OUT>, orquestación vía repo-port
│   ├── ts-ddd-repository/     Repository ports + adaptadores: par Firestore/InMemory, DI token
│   ├── ts-ddd-controller/     Controllers HTTP: rutas, guards, validación Zod, Result→HTTP
│   ├── ts-ddd-domain-service/ Domain services: policies/calculadoras stateless que retornan Result
│   └── ts-query-cqrs/         CQRS de lectura: *Query ports, read use cases find-*, proyecciones
├── packages/                  Paquetes de workspace que no son skills (sin SKILL.md)
│   ├── pm-tasks/              Meta-paquete — instala toda la familia pm-tasks
│   ├── pm-tasks-testkit/      Fakes en memoria para los verbos CRUD canónicos
│   └── ts-ddd/                Meta-paquete — instala toda la familia ts-ddd
├── scripts/                   Validadores, checks de contrato, gate de baseline de skill-judge
├── docs/                      publishing-guide.md
└── .changeset/                Registros de intención de release (workflow Changesets)
```

## Desarrollo local

```bash
make hooks       # una vez — instala lefthook (prettier sobre staged, gitleaks, Conventional Commits)
make validate    # checks de frontmatter + schema + links + paridad de locale
make help        # lista completa de targets
```

> [!TIP]
> El `Makefile` es el punto de entrada canónico — más corto que recordar los nombres de scripts de pnpm y el único exigido por lefthook en el commit.

Las releases siguen el workflow [Changesets](https://github.com/changesets/changesets) — registra la intención con `make changeset`, aplica con `make release-version`, publica con `make release-publish`. Consulta [`.changeset/README.md`](../../.changeset/README.md) para el paso a paso.

## Docs

- [Guía de publicación](../../docs/publishing-guide.md) — cómo se conectan los tres canales de distribución.
- [Workflow Changesets](../../.changeset/README.md) — registrar → versionar → publicar.
- Los deep dives de cada familia viven en el `SKILL.md` y `references/` de cada miembro.

## Licencia

MIT — consulta [LICENSE](../../LICENSE).
