<p align="center">
  <img src="logo.jpg" alt="VR²N Logo" width="200"/>
</p>

<h1 align="center">🚀 DatumSync by VR²N</h1>

<p align="center"><em>
Eliminate bad data. Build real confidence.
</em></p>

---
## 🔗 Visit us at [https://vr2n.com](https://vr2n.com)

**DatumSync** is an intelligent, automated data pipeline platform developed by [VR²N](https://github.com/vr2n) to streamline large-scale data processing. Built with modular architecture and cloud-native design, it supports:

**✅ Validation** • **🌀 Normalization** • **🔁 Conversion** • **🔮 Prediction** • **📊 Profiling**

Backed by FastAPI, Google Cloud, and a powerful real-time dashboard, DatumSync is your all-in-one solution for intelligent data operations.

> *DatumSync is currently in private development. To explore or partner, [contact us](mailto:hello@vr2n.io).*

---

## 🧠 Why DatumSync?

> “A modern enterprise needs more than just pipelines — it needs *intelligence at every step*.”

### ✨ Key Features

- ✅ **Data Validation** — Ensures schema and data integrity
- 🌀 **Normalization** — Standardizes messy datasets
- 🔁 **Conversion** — Automates CSV-to-Parquet transformations
- 🔮 **Prediction** — Uses ML models to infer data outcomes
- 📊 **Profiling** — Auto-generates reports with descriptive stats
- 📈 **Interactive Dashboard** — Visualize pipeline activity in real time
- 💳 **Pro Plan with Stripe** — Unlock unlimited usage and premium features

---

## ⚙️ Tech Stack

| Layer            | Technologies                                                               |
| ---------------- | -------------------------------------------------------------------------- |
| **Backend**       | FastAPI, SQLAlchemy, Authlib                                               |
| **Frontend**      | Jinja2, Tailwind CSS, Chart.js                                             |
| **Cloud Infra**   | Google Cloud Run, Cloud Storage, Pub/Sub, Terraform                       |
| **Data & ML**     | Pandas, Scikit-learn                                                       |
| **Database**      | Supabase PostgreSQL                                                        |
| **Billing**       | Stripe Checkout + Webhooks                                                 |
| **Auth**          | Google OAuth 2.0                                                           |

---

## 🧩 How It Works

```mermaid
graph TD

    A[👤 User Uploads File] --> B["📁 Central GCS Bucket"]
    B --> C["📨 Pub/Sub Event"]
    C --> D["⚡ Eventarc Triggers"]

    D --> E1["🔁 Conversion"]
    D --> E2["🧪 Normalization"]
    D --> E3["✅ Validation"]
    D --> E4["🔮 Prediction"]
    D --> E5["📊 Profiling"]

    subgraph "🧠 Cloud Run Microservices"
        E1 --> F1["Parquet Export"]
        E2 --> F2["Cleaned Output"]
        E3 --> F3["Validated Records"]
        E4 --> F4["ML Outcomes"]
        E5 --> F5["Summary Report"]
    end

    F1 --> DB["📦 Supabase DB (Reports)"]
    F2 --> DB
    F3 --> DB
    F4 --> DB
    F5 --> DB

    DB --> UI["📊 FastAPI Dashboard"]
```
---
```mermaid
graph TD;
    Upload[📤 User Uploads File via UI] --> SaveToDB[(🗃️ Save File Info to PostgreSQL)]
    Upload --> CentralGCS[(☁️ Store in Central GCS Bucket)]

    SaveToDB --> Router{📌 Based on Selected Module}
    Router --> Convert[🔁 Conversion Module]
    Router --> Normalize[🧪 Normalization Module]
    Router --> Validate[✅ Validation Module]
    Router --> Predict[🔮 Prediction Module]
    Router --> Profile[📊 Profiling Module]

    Convert --> UserGCS[(👤 Store in User GCS Bucket)]
    Normalize --> UserGCS
    Validate --> UserGCS
    Predict --> UserGCS
    Profile --> UserGCS

    UserGCS --> UpdateDB[(🗂️ Update Output Path in PostgreSQL)]
    UpdateDB --> Dashboard[User Dashboard & Reports]

```
---
## 🧹 Modules & Routes

| Module        | Endpoint                                      | Description                       |
| ------------- | --------------------------------------------- | --------------------------------- |
| Auth          | `/login`, `/auth/callback`                    | Google OAuth 2.0 Login            |
| Validation    | `/validate`, `/columns`                       | File-based schema and data check  |
| Normalization | `/normalize`, `/normalize-file`               | Standardizes data formats         |
| Conversion    | `/convert`                                    | CSV to Parquet conversion         |
| Prediction    | `/predict`                                    | ML predictions on normalized data |
| Profiling     | `/profile`                                    | Data profiling reports            |
| Dashboard     | `/dashboard`                                  | Interactive stats and graphs      |
| Subscription  | `/subscription`, `/subscribe/pro`, `/success` | Stripe Pro Plan                   |

---
## ☁️ Deployment

This project is deployed via:

* 🔧 **Render (App Hosting)**
* ☁️ **Google Cloud Run (Modular services)**
* 📎 **Stripe (Billing)**
* 📃 **Supabase (PostgreSQL DB & auth)**

---
## 🛡️ Uptime & Reliability
To ensure continuous availability of the application hosted on a free-tier Render instance, a proactive uptime monitoring solution was implemented:

* **🧩 Strategy**
/health Endpoint
A lightweight health-check endpoint (GET /health) was added to confirm app readiness and ensure it responds with HTTP 200 OK.

* **🛠️ Uptime Monitoring with UptimeRobot**
UptimeRobot is used to ping the /health endpoint every 5 minutes, preventing the service from entering cold-start or sleep mode (a common limitation of free-tier platforms).

* **🧠 Benefit**
This setup ensures real-time reliability, faster response times, and uninterrupted user experience — all without requiring paid infrastructure.
```bash
@app.get("/health")
async def health_check():
    return {"status": "ok"}
```
---

## ✅ What's Unique?

* **GCP-native triggers:** Event-driven architecture using Pub/Sub and Cloud Run.
* **Stripe Checkout + Webhooks:** Full billing cycle implemented.
* **Modular cloud pipeline:** Each stage (e.g., validation, prediction) is its own microservice.
* **Real-time dashboard with visual analytics.**

---

## 📌 Google-readiness Highlights

* Full-stack GCP + Python + FastAPI implementation
* Clean modular microservice architecture
* Secure OAuth authentication + database integration
* Production-grade billing system with Stripe
* Optimized for large datasets (500k+ records)
* Dockerized for scalable deployment

---

## 👨‍💻 Author

**Shubham Singh**
MSc Data Science, University of Nottingham
📧 [shubhamsinghvr2n@gmail.com](mailto:shubhamsinghvr2n@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/shubhamsinghvr) | [GitHub](https://github.com/vr2n)

---
