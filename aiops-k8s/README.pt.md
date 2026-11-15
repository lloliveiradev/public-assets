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
