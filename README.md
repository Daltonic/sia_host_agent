# SiaHost Agent

Local-first, non-custodial agentic automation system for Sia storage hosts.

## Overview

SiaHost Agent removes the technical barrier to operating high-performing Sia hosts by automating pricing optimization, collateral management, uptime monitoring, contract selection and infrastructure scaling.

Built on top of `hostd` and `indexd`, this system continuously ingests host and network signals, applies AI reasoning, and executes safe optimizations to maximize host performance and revenue.

## ✨ Key Features

- 🤖 **AI-Powered Optimization**: Autonomous decision making for pricing and collateral
- 📊 **Real-time Analytics**: Live metrics and performance monitoring
- ⚡ **Event-Driven Architecture**: Fast reaction to network conditions
- 🔒 **Non-Custodial**: Runs locally on your infrastructure, no external control
- 🛡️ **Controlled Execution**: Safe operations with approval gates
- 📈 **Built-in Observability**: Comprehensive metrics, logging and alerting

## 🧰 Tech Stack

| Layer | Technologies |
|-------|--------------|
| AI Engine | LangGraph + Claude Sonnet + Qdrant |
| Workflows | Temporal + n8n |
| Backend | FastAPI (Python 3.12) |
| Frontend | Next.js 16 + shadcn/ui |
| Database | PostgreSQL 17 + pgvector + Redis |
| Infrastructure | Docker Compose |
| Observability | Prometheus + Grafana + Loki |

## 🚀 Quick Start

*(Coming Soon)*

## 🏗 System Architecture

9-layer modular design:
1.  **Data Ingestion** - hostd / indexd metrics collection
2.  **AI Intelligence** - Agent decision system
3.  **Workflow Orchestration** - Durable execution engine
4.  **Blockchain Integration** - Sia network interactions
5.  **API Gateway** - Secure command execution layer
6.  **User Interface** - Dashboard and management UI
7.  **Infrastructure** - Containerized deployment
8.  **Persistence** - Database and storage layer
9.  **Observability** - Monitoring and alerting

## 🎯 Success Goals

- +25% increase in active Sia network hosts
- > 99.5% host uptime
- +30% improved contract acceptance rate
- 80% reduction in manual host operator interventions

## 📌 Project Status

Currently in active development. 5 month roadmap:
1.  ✅ Foundation & Data Layer
2.  🔄 Intelligence Layer
3.  ⏳ Workflow Orchestration
4.  ⏳ UX & Observability
5.  ⏳ Hardening & Public Release

## 📄 License

Open Source (Coming Soon)