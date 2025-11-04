# 🧠 JobSeeker AI V2 – System Overview

## 1. Project Summary

### Purpose

JobSeeker AI V2 is an intelligent job application platform designed to help users streamline their career search process. It enables users to:

- Scrape and discover new job listings
- Automatically generate resumes and cover letters
- Apply to positions efficiently
- Prepare for interviews using AI-driven prompts
- Track job applications and progress
- Schedule automated job searches and notifications

### Tech Stack

| Layer | Technology |
|-------|-----------|
| Core / API Gateway | JavaScript / TypeScript (Node.js + Express) |
| Microservices | Python (FastAPI) |
| Frontend | React + Tailwind CSS |
| Database | Supabase (PostgreSQL) |
| Automation | n8n (workflow automation engine) |

This project follows a **Domain-Driven Design (DDD)** and modular architecture approach, ensuring that each service and feature is independently maintainable, testable, and horizontally scalable. It is built for real-world deployability, with attention to performance, fault tolerance, developer clarity, and emerging Green AI initiatives.

---

## 2. System Philosophy

### 🧩 Domain-Driven Design (DDD)

The system is divided into distinct business domains, each owning its own logic, data models, and routes.

| Domain | Description | Technology |
|--------|-------------|------------|
| **User Domain** | Handles authentication, profiles, and credit usage | Supabase Auth / Node.js |
| **Resume Domain** | Manages AI-powered resume and cover letter generation | FastAPI + OpenAI |
| **Job Domain** | Scrapes and organizes job listings and applications | FastAPI + Python |
| **Admin Domain** | Provides usage analytics, logs, and admin reports | Node.js |
| **Automation Domain** | Handles scheduled tasks and notifications | n8n / Celery |

#### Benefits of DDD

- Clear separation of concerns
- Independent feature development and scaling
- Easier maintenance and testing
- Alignment between software modules and real-world business needs

---

### ⚖️ CAP Theorem Focus

**CAP Focus:** Availability + Partition Tolerance (AP)

The system prioritizes **availability** — always returning a response to the user — even if that means some temporary eventual consistency in data synchronization.

#### Strategies Used

- **Caching:** Frequently accessed job data and user preferences are cached for faster responses
- **Asynchronous Jobs:** Background workflows (via n8n) handle scraping, AI generation, and updates
- **Database as Source of Truth:** Supabase (PostgreSQL) maintains data integrity across all domains

---

### 📈 Horizontal Scaling Strategy

The system supports both vertical and horizontal scaling:

- Stateless backend containers (Dockerized services)
- Load balancing across backend and microservices
- Background job processing through n8n queues
- Connection pooling for Supabase / PostgreSQL
- Log aggregation for monitoring and fault recovery

---

## 3. Architecture Summary

- **Frontend:** React + Tailwind CSS
- **Backend / API Gateway:** Node.js (Express, TypeScript)
- **Microservices:** FastAPI (Python)
- **Database:** Supabase (PostgreSQL)
- **Automation Layer:** n8n (for scheduled or async workflows)
- **Authentication:** Supabase Auth + JWT
- **Deployment:** Docker + EC2 / Render + GitHub Actions CI/CD pipeline

---

## 4. Diagrams & Documentation

| Type | File |
|------|------|
| User Stories | `system_architecture_userguide.png` |
| System Architecture | `system_architecture_design.png` |
| Domain Design (DDD) | `domain_design_ddd.png` |
| Database Schema (ERD) | `data_model_erd.png` |
| Deployment Architecture | `deployment_architecture.png` |

---

## 5. Future Scalability Notes

- Introduce caching (Redis / Supabase Edge Functions)
- Add event-driven messaging queues
- Explore multi-region Supabase replication
- Integrate real-time application updates (WebSockets or GraphQL Subscriptions)

---

## 6. Author

**Tatiana Brimm** — Full Stack Developer & AI Automation Engineer

**Version:** 1.0  
**Date:** October 2025

---

## Additional Resources

For questions, contributions, or support, please refer to the project repository or contact the development team.