## 📋 Executive Summary

### Problem Statement

Operating a high-performing Sia host requires continuous optimization of pricing, collateral allocation, uptime guarantees, contract selection, and infrastructure scaling. This complexity creates a technical barrier that excludes non-technical operators, ultimately limiting decentralization, storage supply growth, and network reliability.

### Solution Overview

**SiaHost Agent** is a **local-first, non-custodial, agentic automation system** built on top of hostd and indexd. It combines:

- Event-driven architecture
- AI-powered decision systems (LangGraph + Claude Sonnet)
- Durable workflow orchestration (Temporal)
- Self-hosted automation (n8n)

The system continuously ingests host + network signals, reasons over them, and executes safe optimizations via controlled hostd interactions.

### Success Metrics

- +25% increase in active Sia hosts
- > 99.5% uptime
- +30% contract acceptance rate
- 80% reduction in manual interventions
- Measurable TB growth in network capacity

---

# 🏛 SYSTEM ARCHITECTURE (PRODUCTION BLUEPRINT)

## Architecture Style

- Event-Driven Modular Monolith
- Agent-Orchestrated Decision System
- Local-first with hybrid AI execution

---

## 🔷 LAYERED ARCHITECTURE (9-LAYER MODEL)

### L01 — DATA & INGESTION

**Responsibilities:**

- hostd metrics ingestion
- indexd network insights
- webhook/event collection

**Components:**

- Metrics & Webhook Collector
- indexd Insights Service

**Outputs:**

- Normalized event streams

---

### L02 — AI & INTELLIGENCE

**Responsibilities:**

- Decision making
- Pattern detection
- Optimization strategy

**Stack:**

- LangGraph
- Claude Sonnet (hybrid fallback)
- Qdrant (vector memory)
- MCP Tool Server

**Core Agents:**

- OptimizerAgent
- Pricing & Collateral Optimizer
- Scaling Advisor

---

### L03 — WORKFLOW & AUTOMATION

**Responsibilities:**

- Orchestrate execution
- Ensure durability
- Manage retries

**Stack:**

- Temporal (durable execution)
- n8n (trigger + automation layer)

**Key Concepts:**

- Activities
- Workflows
- Worker Pools

---

### L04 — BLOCKCHAIN & TRUST

**Responsibilities:**

- Contract monitoring
- Network validation

**Network:**

- Sia Network (hostd + indexd)

**Key Concepts:**

- Storage contracts
- Proof validation

---

### L05 — BACKEND / API

**Stack:**

- FastAPI (Python 3.12)
- Pydantic v2

**Responsibilities:**

- API Gateway
- Auth & RBAC
- Command execution layer

---

### L06 — INTERFACE & UX

**Stack:**

- Next.js 16
- shadcn/ui

**Components:**

- Dashboard
- Onboarding Wizard
- Real-time analytics UI

---

### L07 — INFRASTRUCTURE

**Stack:**

- Docker Compose
- VPS (Hetzner/DigitalOcean)
- Traefik

---

### L08 — DATABASE & PERSISTENCE

**Stack:**

- PostgreSQL 17 + pgvector

**Data Domains:**

- Metrics
- Contracts
- Actions
- Alerts

---

### L09 — OBSERVABILITY

**Stack:**

- Prometheus
- Grafana
- Loki
- LangSmith / LangFuse

---

# 🔄 SYSTEM FLOW (9-STEP EXECUTION MODEL)

1. Data Ingestion → hostd + indexd streams
2. AI Reasoning → agent evaluates signals
3. Workflow Trigger → Temporal workflow starts
4. Blockchain Sync → contract state verified
5. API Execution → action validated
6. UI Update → state reflected
7. Infra Execution → container-level updates if needed
8. Data Persistence → DB write + cache
9. Observability → metrics + alerts triggered

---

# 🧠 AI AGENT SYSTEM DESIGN

## Core Agents

### OptimizerAgent

- Goal: Maximize revenue + uptime
- Authority: Controlled write access

### Pricing & Collateral Optimizer

- Adjusts pricing dynamically

### Scaling Advisor

- Suggests hardware upgrades

---

## MCP TOOL SERVER (CRITICAL)

### Tools Exposed

- adjust_pricing
- set_collateral
- update_config
- fetch_metrics

### Flow

Agent → MCP Client → MCP Server → hostd RPC → Response

---

## Memory Architecture

- Short-term: Redis
- Long-term: Qdrant vector DB

---

# ⚙️ WORKFLOW DESIGN (TEMPORAL)

## Example Workflow

Optimization Workflow:

1. Fetch metrics
2. Evaluate thresholds
3. Generate strategy
4. Execute action
5. Validate result

## Retry Policy

- Exponential backoff
- Max retries: 5

## Failure Handling

- Dead Letter Queue
- Alert trigger

---

# 🗄 DATA MODEL (EXPANDED)

## Tables

### hosts

- id
- config
- status

### metrics

- id
- uptime
- revenue
- storage_used
- timestamp

### actions

- id
- type
- payload
- status

### alerts

- id
- severity
- message

### contracts

- id
- value
- duration
- risk_score

---

# 🔌 API SPECIFICATION

## Auth

- JWT-based local auth

## Endpoints

### POST /onboard

Initializes host setup

### GET /metrics

Returns host metrics

### POST /optimize/run

Triggers optimization

### GET /alerts

Returns alerts

### POST /config/update

Applies configuration changes

---

# 🔐 SECURITY MODEL

## Principles

- Non-custodial
- Local-first
- Zero external data leakage

## Controls

- RBAC
- Signed actions
- Audit logs

---

# ☁️ INFRASTRUCTURE DESIGN

## Deployment Model

- Docker Compose (single-node)

## Services

- API
- Redis
- PostgreSQL
- Qdrant
- Temporal
- n8n

---

# 📡 OBSERVABILITY DESIGN

## Metrics

- uptime
- revenue
- contract success rate

## Alerts

- downtime
- failed optimization

---

# 🗓 6-MONTH IMPLEMENTATION PLAN

## Milestone 1 — Foundation (Month 1)

- Repo setup
- Core infra
- API skeleton

## Milestone 2 — Data Layer (Month 2)

- Metrics ingestion
- PostgreSQL schema

## Milestone 3 — Agent MVP (Month 3)

- Basic optimizer
- MCP tools

## Milestone 4 — Workflow Engine (Month 4)

- Temporal integration
- Retry logic

## Milestone 5 — UX + Alerts (Month 5)

- Dashboard
- Alert system

## Milestone 6 — Hardening & Launch (Month 6)

- Security
- Testing
- OSS release

---

# ⚠️ RISKS & MITIGATIONS

| Risk                   | Mitigation                        |
| ---------------------- | --------------------------------- |
| Incorrect AI decisions | Rule constraints + approval layer |
| hostd API changes      | Adapter abstraction               |
| Workflow failures      | Temporal durability               |
| Data inconsistency     | Event sourcing                    |


