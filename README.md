# 🚀 SaaS AI Platform – Multi-Tenant RAG + LLM + MCP (Spring AI)

## 📌 Overview

This project is a **Production-Ready Multi-Tenant AI SaaS Platform** built using:

- Spring Boot 3
- Spring AI
- LLM (OpenAI / Cohere)
- Retrieval-Augmented Generation (RAG)
- PgVector (Vector Database)
- Kafka (Event-driven architecture)
- Redis (Rate limiting + caching)
- JWT Authentication
- MCP Tool Integration
- Docker + Kubernetes

It enables enterprises to build their own **AI-powered Knowledge Copilot** with secure tenant isolation and scalable infrastructure.

---

## 🎯 Problem Statement

Modern enterprises struggle with:

- 📚 Large volumes of internal documentation
- 🧑‍💻 Slow knowledge retrieval across teams
- 🔐 Security concerns around AI tools
- 🏢 Multi-tenant SaaS isolation complexity
- 🔄 Need for external tool integrations (CRM, Orders, Billing APIs)
- 📈 Usage tracking and monetization

This platform solves these challenges by providing:

- Secure multi-tenant RAG
- Enterprise knowledge grounding
- Tool calling via MCP
- Rate limiting and usage tracking
- Scalable cloud-native architecture

---

## 🧠 What This Platform Does

### ✅ Multi-Tenant AI Assistant
Each tenant has isolated:
- Documents
- Embeddings
- Conversations
- Usage tracking

### ✅ Retrieval-Augmented Generation (RAG)
- Documents are embedded
- Stored in PgVector
- Retrieved semantically
- Used as context for LLM responses

### ✅ MCP Tool Integration
AI can call external systems such as:
- Order status APIs
- CRM systems
- Billing services
- Custom enterprise tools

### ✅ Secure SaaS Architecture
- JWT authentication
- Tenant-based filtering
- Redis rate limiting
- Kubernetes-ready deployment

### ✅ Event-Driven Scalability
Kafka enables:
- Async ingestion
- AI processing queues
- Usage tracking
- Analytics pipeline

---

## 🏢 Real-World Use Cases

### 🏦 Banking Knowledge Copilot
Employees ask:
> “What is the process for loan pre-approval?”

AI retrieves internal policy documents and responds accurately.

---

### 🛒 E-Commerce Support Assistant
Customer asks:
> “Where is my order?”

AI:
- Retrieves order data via MCP tool
- Provides real-time status

---

### 🏥 Healthcare Compliance Assistant
Doctors ask:
> “What is the latest compliance update?”

AI retrieves official compliance documentation.

---

### 🧑‍💼 Enterprise Developer Copilot
Developers ask:
> “How do we deploy microservices internally?”

AI retrieves internal DevOps documentation.

---

## 🏗 Architecture

               +---------------------+
               |   API Gateway       |
               +---------------------+
                          |
                          v
               +---------------------+
               |   AI Service        |
               | (RAG + LLM)         |
               +---------------------+
                  |        |       |
                  v        v       v
             PgVector   Redis    Kafka
                  |
               PostgreSQL



---

## 📦 Microservices

| Service | Responsibility |
|----------|---------------|
| gateway-service | Routing + security |
| auth-service | JWT authentication |
| ai-service | LLM + RAG orchestration |
| ingestion-service | Document embedding |
| mcp-tool-server | External tool integration |
| common-lib | Shared DTOs & utilities |

---

## 🔐 Security Features

- JWT-based authentication
- Tenant isolation via metadata filtering
- API keys via environment variables
- Kubernetes secret support
- Rate limiting per tenant
- Input validation
- Prompt injection guardrails (planned)

---

## 📊 Tech Stack

| Layer | Technology |
|--------|-----------|
| Backend | Spring Boot 3 |
| AI | Spring AI |
| LLM | OpenAI / Cohere |
| Vector DB | PgVector |
| Database | PostgreSQL |
| Cache | Redis |
| Messaging | Kafka |
| Security | Spring Security + JWT |
| Container | Docker |
| Orchestration | Kubernetes |
| Observability | Actuator + Prometheus |

---

## 🚀 How to Run Locally

### 1️⃣ Start Infrastructure

```bash
docker-compose up -d
```
This starts:

PostgreSQL (PgVector)

Redis

Kafka

2️⃣ Set Environment Variables
```bash
export OPENAI_API_KEY=your_key
export JWT_SECRET=your_secret
```

3️⃣ Build Project
```bash
mvn clean install
```

4️⃣ Start Services

Start services individually or via Docker.
