# Boško Radivojević – Backend Engineer

Building enterprise-grade backend systems for ERP, invoicing, and automation across 5 Balkan markets.  
Currently **Head of Software Development @ Elastyc Net** (Belgrade).

---

## 🚀 Featured Projects

### [SEF E‑Invoice Integration](https://github.com/BRadivojevic/sef-einvoice-php)
> Automated XML e‑invoice generation, validation, and SEF API submission.  
> Handles over 20K invoices monthly with less than 1% error rate.

**Highlights**
- Outbound invoice management (send individually or in bulk)
- Real‑time status tracking and filtering
- Inbound invoice management with approve/reject workflows
- XML/PDF attachments and full SEF synchronization
- Automated retrieval of unseen invoices directly from SEF API

**Tech Stack:** PHP 8 · Guzzle 7 · XML / UBL 2.1 · JSON Logging · SQL Server / SQLite

**UI Screenshots**

| Outbound Invoices | Outbound Invoice Details |
|:--|:--|
| ![Outbound invoices](https://raw.githubusercontent.com/BRadivojevic/sef-einvoice-php/main/docs/outbound-invoice-sc-1.png) | ![Outbound invoice details](https://raw.githubusercontent.com/BRadivojevic/sef-einvoice-php/main/docs/invoice-sc-1.png) |

| Inbound Invoices | Inbound Invoice Details |
|:--|:--|
| ![Inbound invoices](https://raw.githubusercontent.com/BRadivojevic/sef-einvoice-php/main/docs/inbound-invoice-sc-1.png) | ![Inbound invoice details](https://raw.githubusercontent.com/BRadivojevic/sef-einvoice-php/main/docs/inbound-invoice-sc-2.png) |

---


# [Elasticsearch Reindex Worker](https://github.com/BRadivojevic/php-elasticsearch)
> High-throughput reindexing and data ingestion system for Elasticsearch 7.17.x and SQL Server 2019+.  
> Handles millions of rows per job with zero downtime, background workers, and idempotent upserts via `acckey`.

## 🧠 Overview
This project is a production-grade PHP reindexing system built for large SQL Server datasets synchronized into Elasticsearch.  
It automatically batches records, retries failed bulk operations, and uses background workers to bypass 524/534 Cloudflare timeouts.  
It was engineered for resilience, scalability, and correctness in real business environments.

## ⚙️ Highlights
- 🚀 Background workers — long jobs run outside HTTP, safe from Cloudflare limits  
- 🧩 Batching with ROW_NUMBER() / OFFSET — handles multi-million-row tables  
- 🔁 Idempotent upserts — every document uses acckey as Elasticsearch _id  
- 💾 Job queue — file or SQL Server-based persistence  
- ⚖️ Retry logic + dead-letter queue for bad docs  
- 🧹 Normalization of dates, nulls, and diacritics  
- 📊 JSON logging for dashboards and traceability  

## 🚀 Quick Start

1️⃣ Install dependencies
```bash
composer install
```

2️⃣ Copy `.env.example` → `.env`
```env
ES_HOSTS=http://localhost:9200
MSSQL_HOST=localhost
MSSQL_DB=benussi
MSSQL_USER=sa
MSSQL_PASSWORD=YourStrong!Passw0rd
```

3️⃣ Enqueue a reindex job
```bash
POST /public/queue-reindex.php
{
  "source_index": "benussi_flota_source",
  "dest_index": "benussi_flota_target",
  "tenant": "flota"
}
```

4️⃣ Run the background worker
```bash
php workers/reindex_worker.php
```

or directly import SQL data:
```bash
php workers/insert_bulk_worker.php index=benussi_flota sql=examples/select_batch_row_number.sql start=1 end=10000
```

## 🧩 Data Normalization
All SQL data is sanitized before indexing:
- Empty or 1900-01-01 → null  
- Diacritics normalized (č → c, ž → z, đ → dj)  
- Trims and type normalization for safe ingestion

## 🪣 Dead-Letter Handling
Invalid or failed documents (e.g., missing acckey, ES bulk errors) are saved to:
```
var/deadletter.jsonl
```
Each line contains the failed document and error cause — perfect for post-analysis.

## 🧱 Example SQL Batching

**ROW_NUMBER version**
```sql
WITH src AS (
  SELECT ROW_NUMBER() OVER (ORDER BY [Id]) AS rn, *
  FROM dbo.LargeTable WITH (NOLOCK)
)
SELECT * FROM src
WHERE rn BETWEEN ? AND ?;
```

**OFFSET/FETCH version**
```sql
SELECT *
FROM dbo.LargeTable WITH (NOLOCK)
ORDER BY [Id]
OFFSET ? ROWS FETCH NEXT ? ROWS ONLY;
```

## 📊 Dashboards & KPIs
| Fleet Dashboard | Sales KPI Dashboard |
|:--|:--|
| ![Fleet dashboard](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-dash-sc-1.png) | ![Sales KPI dashboard](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-dash-sc-2.png) |

## 🗂 Elasticsearch Tables
| Modules Reindex Table | Global Reindex Table |
|:--|:--|
| ![ES reindex modules](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-sc-1.png) | ![ES global reindex table](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-sc-3.png) |

## 👤 Author
**Boško Radivojević**  
[github.com/BRadivojevic](https://github.com/BRadivojevic)  

MIT License © 2025


### [DocuSign Integration (PHP)](https://github.com/BRadivojevic/docusign-integration-php)
> Advanced DocuSign automation platform integrating OAuth2, envelope queuing, and secure webhooks.  
> Enabled same‑day digital contract completion and background‑safe processing for large-scale deployments.

**Highlights**
- Full OAuth2 flow (authorization code with PKCE support)
- Background envelope worker with retry and dead‑letter handling
- Secure webhook validation (HMAC SHA‑256)
- Supports file and SQLite job stores
- Designed for production DocuSign environments

**Tech Stack:** PHP 8 · DocuSign SDK 6.x · Guzzle · SQLite / File Queue · REST API · JSON Logging

---

## 🧠 Skills
**Languages / Frameworks:** PHP 8 · SQL Server · Elasticsearch · jQuery · AJAX  
**APIs & Integrations:** SEF API · DocuSign · Pantheon ERP · Postmark · TecAlliance · OpenAI · Google  
**DevOps:** GitHub Actions  
**Tools:** Postman · Git · Tabulator.js · XML processing  
*(Expanding into Python/FastAPI & cloud data pipelines.)*

---

## 🧩 About Me
Backend engineer specializing in enterprise automation and ERP integrations.  
Experienced in leading small backend teams, designing scalable data pipelines, and optimizing search infrastructure.

📍 Belgrade, Serbia (UTC+1)  
📧 [b.radivojevic00@gmail.com](mailto:b.radivojevic00@gmail.com)  
🔗 [LinkedIn](https://linkedin.com/in/bosko-radivojevic-94a783238)
