# Awesome-Multi-Agent-System-Builders

# Top Multi-Agent System Builders Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Visual Agent Orchestration, No-Code Builder Interfaces & Cross-Cloud Deployment*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Multi-Agent System Builders**. These tools provide the visual interfaces, declarative configuration layers, and deployment runtimes that let teams design, test, and ship systems where multiple AI agents collaborate — without writing orchestration code from scratch or locking into a single cloud vendor's proprietary agent SDK.

**Examples** include Microsoft Copilot Studio, Salesforce Agentforce, Amazon Bedrock Agents, Google Vertex AI Agent Builder, and the open-source builders that give you the same capabilities without vendor lock-in.

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, visual workflow design, and framework-agnostic deployment — ideal for platform engineers who want to build multi-agent systems that run on any cloud, with any agent framework, under their own governance.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Microsoft Copilot Studio** — Microsoft's low-code platform for building conversational agents and multi-agent workflows within the Microsoft 365 ecosystem. Deep integration with Azure OpenAI, Teams, and Power Platform. **Best for Microsoft-centric organizations** wanting managed agent building with enterprise identity and compliance built in.

- **Salesforce Agentforce** — Salesforce's agent platform for building autonomous agents on the Salesforce platform. Agents can access CRM data, execute actions, and collaborate across service, sales, and marketing use cases. **Best for Salesforce customers** wanting agents tightly coupled to their CRM data and workflows.

- **Amazon Bedrock Agents** — AWS's managed service for building agents that can execute multi-step tasks using foundation models, APIs, and knowledge bases. **Best for AWS-native teams** wanting managed agent orchestration within the Bedrock ecosystem.

- **Google Vertex AI Agent Builder** — Google Cloud's agent building platform with Agent Development Kit (ADK) for code-first agent creation and visual tools for prototyping. **Best for GCP-native organizations** building agents on Gemini models.

- **ServiceNow Now Assist** — ServiceNow's AI agent platform for automating IT service management, customer service, and HR workflows with multi-agent coordination. **Best for ServiceNow customers** wanting agents embedded in existing ITSM processes.

## Open-Source GitHub Projects

- **[GenXAI](https://pypi.org/project/genxai-framework/)**  
  **The graph-first multi-agent framework with a roadmap to no-code visual building** — OSS package ships a **`genxai` CLI** for tool and workflow management, plus a Python library for programmatic agent definition . **Graph engine** for complex orchestration similar to LangGraph, with **AgentRegistry**, **Graph**, **InputNode/OutputNode/AgentNode**, and **Edge** primitives . **Flow orchestrators** for common patterns: **RoundRobinFlow**, **SelectorFlow**, and **P2PFlow** with consensus thresholds . **Enterprise-grade cross-cutting concerns** designed in from the start: **RBAC, policy engine, audit logging, guardrails (PII, filters), and secrets/encryption** . **No-code Studio is Phase 3 of the roadmap** (weeks 9-12), with a visual workflow builder, REST API, and real-time testing planned . **CLI commands** include `genxai tool list`, `genxai tool search`, `genxai workflow run examples/nocode/content_generation.yaml` . **Best for teams wanting graph-based orchestration today** with a clear path to visual building, and enterprise governance baked into the architecture rather than bolted on later.

- **[Corteza @Human](https://docs.planetcrust.com/corteza-low-code)**  
  **The open-source Salesforce alternative adding multi-agent capabilities** — Corteza is used by thousands of organizations including Fortune 100 businesses and government institutions . **@Human is a fully integrated feature layer on top of Corteza's core** allowing organizations to **safely build, deploy and manage multi-agent infrastructures, automation and third-party connectivity** . **All features remain Apache 2.0 open source** . **Corteza's build logic mirrors Salesforce Lightning**, making it the natural migration path for teams leaving Salesforce but wanting similar low-code application building with multi-agent additions . **Throughout 2026, @Human will become 100% backward compatible with all Corteza features**, with each exposed AI feature thoroughly tested before release . **Best for organizations wanting a proven low-code platform** (Corteza) with an emerging multi-agent layer (@Human) under Apache 2.0, especially Salesforce refugees.

- **[Docker cagent](https://pkg.go.dev/github.com/docker/cagent)**  
  **The declarative YAML-based multi-agent builder from Docker** — **no code required**: define agents in YAML, give them tools, and let them work . **Multi-agent architecture** creates teams of specialized agents that delegate tasks automatically . **Rich tool ecosystem**: built-in tools plus any MCP server (local, remote, or Docker-based) . **AI provider agnostic**: OpenAI, Anthropic, Gemini, AWS Bedrock, Mistral, xAI, Docker Model Runner, and more . **YAML configuration is declarative, versionable, shareable** . **Advanced reasoning**: built-in think, todo, and memory tools . **RAG**: pluggable retrieval with BM25, embeddings, hybrid search, and reranking . **Package and share**: push agents to any OCI registry, pull and run them anywhere . **Install**: pre-installed with Docker Desktop 4.49+, via Homebrew, or binary releases . **Quick start**: `cagent new` to generate interactively, or `cagent run agentcatalog/pirate` from the catalog . **Best for Docker-native teams** wanting declarative multi-agent systems that ship like containers.

- **[AgentBreeder](https://pypi.org/project/agentbreeder/)**  
  **The deploy-and-govern layer that works with any agent framework** — **Apache 2.0 licensed** . **"AgentBreeder is to agents what Docker + Kubernetes is to microservices"** — your agent framework is the application, AgentBreeder is the platform . **Framework lock-in: none** — bring LangGraph, CrewAI, OpenAI, Claude, Google ADK, or custom agents, wrap them in an `agent.yaml`, and deploy . **Cloud lock-in: none** — same YAML deploys to AWS, GCP, local, or Kubernetes . **Governance built in**: RBAC, audit, and cost tracking automatic, with **org-wide registry** for agents, tools, prompts, and models . **Multi-agent orchestration** with 6 strategies (router, sequential, parallel, hierarchical, supervisor, fan-out) across frameworks . **MCP native**: Hub + sidecar injection . **Cost attribution per team/agent/model** . **Explicitly contrasts with managed platforms**: AWS Bedrock Agents, Vertex AI Agent Builder, and Azure AI Agent Service all require rewriting your agent in their SDK and deploying to their cloud — AgentBreeder keeps your code and your cloud . **Best for organizations with existing agents** wanting a governance and deployment layer without rewriting everything for each cloud.

- **[Harnis](https://pypi.org/project/harnis/)**  
  **The multi-tenant agent runtime with SSO, RBAC, and per-tenant cost limits** — **tenant always comes from the verified token, never from the request** . **Role-based access**: user (talk to agents), reviewer (approve/deny actions, view analytics), admin (prompts, API keys, audit log), platform-admin (manage tenants) . **OIDC console sign-in** with PKCE, no client secret, strict CSP . **Service API keys** for CI/integrations, stored only as hashes . **Per-tenant `allowed_providers`** limits where prompts may be sent, and **`max_cost_usd_per_turn`** enforces cost ceilings . **Plugin system** for custom tools and agents via `AgentSpec` and `Tool` registration . **Best for teams building multi-tenant agent platforms** where tenant isolation, governance, and cost control are non-negotiable.

- **[Agent Guild](https://pypi.org/project/agent-guild/)**  
  **The project installer that bootstraps a full multi-agent development environment** — installs agents, skills, memory, and MCP servers for Claude Code, Cursor, and Codex from a single command . **Language coders** for Python, Swift, and TypeScript add code-navigation MCP servers (`codenav-mcp`, `codenav-swift-mcp`, `webnav-ts-mcp`) with AGENTS.md rules routing work to them . **Components**: `sdd` (spec-driven development), `memory-bank`, `jevmem` (memory server), and `code-grader` . **Never overwrites differing files** — safe to run on projects with existing setups . **`--dry-run`** shows the plan without writing . **Best for teams wanting a batteries-included multi-agent coding setup** across multiple agentic IDEs without manual configuration.

### Additional Strong Open-Source Options

- **Lurawi** — NoCode/LowCode visual workflow builder for agent-based workflows. **Drag-and-drop canvas** compiles to XML/JSON for deployment on the Lurawi runtime engine in Docker. **REST API, modular custom function classes, and cloud-ready deployment** . Best for teams wanting a visual editor that compiles to deployable artifacts .
- **Cerebrum (AIOS SDK)** — NAACL 2025 paper-backed platform with SDK, Agent Hub for sharing/discovering agents, and interactive web interface for testing. **Modular four-layer architecture** (LLM, memory, storage, tool management) with implementations of CoT, ReAct, and tool-augmented agents . Best for researchers wanting a standardized agent development platform with community sharing .

**Frameworks for building custom systems**: Combine **GenXAI** for graph-first orchestration with a visual-building roadmap and built-in governance, **Docker cagent** for declarative YAML-defined multi-agent systems that ship like containers, **AgentBreeder** for framework- and cloud-agnostic deployment with automatic governance, **Harnis** for multi-tenant runtime isolation with SSO and cost limits, and **Corteza @Human** for a low-code platform with emerging multi-agent capabilities under Apache 2.0 — to build a multi-agent system builder stack tailored to your deployment model, governance requirements, and existing agent investments.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Multi-agent system builders differ significantly in abstraction level, deployment model, and lock-in risk. **Managed platforms (Copilot Studio, Agentforce, Bedrock Agents, Vertex AI Agent Builder) offer convenience at the cost of cloud and SDK lock-in** — migrating away requires rewriting your agent in a different SDK . **AgentBreeder explicitly positions against this tradeoff**, keeping your agent code and cloud while adding deploy and governance layers . **GenXAI's no-code Studio is roadmap, not shipped** — the OSS package currently provides CLI and Python library access to graph orchestration . **Docker cagent is declarative and container-native** but expects Docker or Homebrew installation and API keys for model providers . **Harnis is multi-tenant runtime infrastructure**, not a visual builder — it assumes you have agents to run. **Corteza @Human is still maturing through 2026** with backward compatibility planned, so evaluate feature completeness against your timeline . **"Multi-agent" is often marketing** — a well-designed single agent with good tools frequently outperforms a poorly-orchestrated team of agents .
- Self-hosted open-source solutions require proper identity provider configuration (OIDC for Harnis), container registry access for cagent, and governance policy definition before production deployment.

---

**Made for platform engineers and AI teams building multi-agent systems without vendor lock-in.**
Let's make multi-agent system builders more open, portable, and governance-ready.
