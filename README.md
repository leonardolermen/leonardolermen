# Leonardo Lermen

**Backend engineer from Brazil** · Java & Spring · payments, risk and distributed systems · building tools that let AI agents ship code safely.

I like backend work where being *almost* right is not an option: money that has to reconcile, webhooks that must arrive once per event, risk decisions that a regulator can audit. I write the decisions down (ADRs, specs) and keep the reasoning next to the code.

---

## What I'm building

### 💳 Payments platform

| Project | What it is | Stack |
|---|---|---|
| [**payment-gateway**](https://github.com/leonardolermen/payment-gateway) | Payment orchestrator: one API for merchants, several providers behind it, and the money never passes through it (merchants use their own bank credentials). Pix and Bolecode through Itaú, credit card through Cielo, with customers, orders, plans and subscriptions on top. Encrypted merchant credentials, masked structured logs, mTLS webhooks and mock providers for development without bank sandboxes. | Java · Spring Boot · PostgreSQL · Docker |
| [**payment-gateway-web**](https://github.com/leonardolermen/payment-gateway-web) | Merchant panel and hosted checkout for the gateway. | React 19 · TypeScript · Vite · Tailwind |
| [**webhook-delivery**](https://github.com/leonardolermen/webhook-delivery) | Library for signed webhook delivery: retry with backoff, ordering by key, idempotency per (event, endpoint), secret rotation with an overlap window, and a per-endpoint concurrency cap so one partner being down doesn't starve the rest. Extracted from Barrier and published as a package. | Java · Spring Boot · virtual threads |

### 🛡️ [Barrier](https://github.com/leonardolermen/Barrier)

KYC / AML risk platform built around Brazilian Central Bank rules. A partner sends a customer, and Barrier runs identity verification, PEP and sanctions screening and risk classification, answering right away (`202`) and again by signed webhook when the analysis finishes. It never stores document images or biometrics, only the outcome of each check, so a leak can't expose data that can't be revoked.

`Java 25` · `Spring Boot 4` · `Kafka (choreography + outbox)` · `PostgreSQL + Flyway` · `ADRs`

### 🪐 Solaris *(private)*

A self-hosted hub where teams of AI coding agents (Claude Code and Codex) work on my repositories, and where I watch what they ship:

- every task runs in its own git worktree and branch; a team (plan → build → review) is reviewed and approved as one unit, with a single PR;
- review comes with a **live preview** of the change and a chat to ask for adjustments, plus automatic tests and a **visual check** (headless browser, desktop and mobile) before anything reaches me;
- the agents' prompts and skills improve themselves from evidence (rejections, review comments, failed checks), versioned and reversible;
- an **API gateway** (routing, failover, JWT / API keys / mTLS, caching) and **OpenTelemetry observability** (traces, logs, metrics, anomaly detection) for the services it runs;
- a Windows desktop app that rebuilds itself from the repository.

`Go` · `templ + htmx` · `SQLite` · `OpenTelemetry` · `MCP`

---

## Tools I reach for

- **Languages:** Java, Go, TypeScript, Python
- **Backend:** Spring Boot, REST, Kafka, PostgreSQL, Flyway
- **Frontend:** React, Vite, Tailwind, htmx
- **Infra & quality:** Docker, GitHub Actions, OpenTelemetry, WireMock, Testcontainers
- **AI engineering:** Claude Code, Codex, MCP servers, multi-agent orchestration

---

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Leonardo%20Lermen-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/leonardo-lermen-768769242/)
