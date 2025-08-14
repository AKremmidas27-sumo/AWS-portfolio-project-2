# AWS-portfolio-project-2

# Serverless Notes API 
(AWS SAM · API Gateway · Lambda · DynamoDB)

A tiny, production-style Notes API you can deploy in minutes. It’s fully serverless, free-tier friendly, and easy to tear down. Great for showcasing API design, IaC, and AWS skills.

## Features
- Endpoints: 'POST /notes', 'GET /notes/{id}\', 'PUT /notes/{id}', 'DELETE /notes/{id}', 'GET /notes' (list by user)
- Simple “auth” for demo: pass a header `x-user-id` (defaults to `demo-user`)
- IaC via **AWS SAM** (`template.yaml`)
- Logging in CloudWatch; On-Demand DynamoDB (no capacity planning)

---

Architecture

Project 2 — Serverless Notes UI (S3 + CloudFront)

A tiny one-file web app that calls the Serverless Notes API from Project 2.

Live demo: `https://<your-cloudfront-domain>/notes/index.html`  
Backend API: API Gateway (HTTP API) → Lambda (Python) → DynamoDB (on-demand), deployed with AWS SAM.

How it works
- Frontend is just `index.html` (vanilla JS + fetch).
- Requests include `x-user-id` header (defaults to `demo-user` if not set).
- CORS is enabled on the API via SAM `CorsConfiguration`.

Endpoints used
- `POST /notes` — create
- `GET /notes` — list for user
- `GET /notes/{id}` — read
- `PUT /notes/{id}` — update
- `DELETE /notes/{id}` — delete

