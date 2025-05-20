# ✅ dinegrid-infra – Infrastructure Setup for DineGrid Microservices

This repository contains **Docker-based infrastructure configurations** for the DineGrid microservices platform. It provisions isolated containers for services, databases, Kafka messaging, and optional admin tools for local development.

---

## 🍽️ Microservices & Components

| Service                  | Port  | Depends On       |
|:-------------------------|:-------|:----------------|
| **food-ordering-service** | `8081` | PostgreSQL (5434) |
| **menu-service**          | `8082` | PostgreSQL (5433) |
| **order-service**         | `8083` | MongoDB (27017)   |
| **Kafka Broker**          | `9092` | Zookeeper (2181)  |
| **Zookeeper**             | `2181` | -                |
| **pgAdmin** (optional)    | `5050` | PostgreSQL        |

---

## 📦 Volumes & Data Persistence

- `food_ordering_pgdata` — Persistent volume for food-ordering-service PostgreSQL  
- `menu_pgdata` — Persistent volume for menu-service PostgreSQL  
- `order-mongo-data` — Volume for MongoDB  
- `kafka-data` — Volume for Kafka logs (optional)

---

## 🚀 Getting Started

1️⃣ Clone this infra repo:
git clone https://github.com/neeldolas/dinegrid-infra.git
cd dinegrid-infra
2️⃣ Run the full Docker stack:

docker-compose up --build -d
💡 Tip:
To clean up orphan containers after removing services:

docker-compose up -d --remove-orphans
🌍 Access Local Services
Service	URL
Food Ordering	http://localhost:8081/swagger-ui.html
Menu Service	http://localhost:8082/swagger-ui.html
Order Service	http://localhost:8083/swagger-ui.html
pgAdmin (optional)	http://localhost:5050

📡 Kafka Messaging Setup
Kafka Broker: kafka:9092

Zookeeper: zookeeper:2181

Topics: order-events (currently configured)

Add new topics or consumers inside your service configs.

🔥 Coming Soon
✅ Redis integration for caching sessions/tokens

✅ API Gateway / Nginx reverse proxy with TLS

✅ CI/CD pipeline configs

✅ Health checks and centralized logging via CloudWatch or ELK

📑 Notes
Ensure Docker Desktop is installed and running.

All services run in a shared Docker network for service name resolution (like kafka:9092 or menu-service:8082).

Environment-specific properties managed within each service’s application.properties or externalized via Docker environment variables.

pgsql
Copy
Edit
