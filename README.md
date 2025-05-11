✅ dinegrid-infra – Infrastructure Setup for DineGrid Microservices
This repository contains all infrastructure configuration files for the DineGrid microservices project. It manages Docker-based local environments for services like:

🍽️ food-ordering-service

🧾 menu-service

🛒 order-service

🗃️ Databases (PostgreSQL, MongoDB)

🚀 Getting Started
1. Clone this repo
git clone https://github.com/neeldolas/dinegrid-infra.git
cd dinegrid-infra
2. Run Docker Compose
docker-compose up --build -d

⚙️ Services Overview
Service Name	       Port	   Depends On
food-ordering-service	8081	 PostgreSQL (5434)
menu-service	        8082	 PostgreSQL (5433)
order-service	       8083	   MongoDB (27017)
pgAdmin (optional)	5050	   PostgreSQL

📦 Volumes & Containers
food_ordering_pgdata – Persistent volume for food-ordering-service PostgreSQL

menu_pgdata – Persistent volume for menu-service PostgreSQL

order-mongo-data – Volume for MongoDB (if included)

🌍 Access Services
Food Ordering Swagger: http://localhost:8081/swagger-ui.html

Menu Swagger: http://localhost:8082/swagger-ui.html

Order Swagger: http://localhost:8083/swagger-ui.html

pgAdmin: http://localhost:5050 (if running)

🛠️ Future Setup Plans
Kafka setup for async messaging

Redis for caching sessions/tokens

Nginx reverse proxy with TLS

CI/CD deployment configs
