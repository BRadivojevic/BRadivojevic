
# Boško Radivojević — Backend & Automation Engineer

Building enterprise-grade backend systems for ERP, invoicing, and automation across 5 Balkan markets.  
Currently **Head of Software Development @ Elastyc Net** (Belgrade).

---

## 🚀 Featured Projects

A selection of production systems built for enterprise automation, document workflows, and data pipelines.

---

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

### [Elasticsearch Reindex Worker](https://github.com/BRadivojevic/php-elasticsearch)
> High-throughput reindexing and data ingestion system for Elasticsearch 7.17.x and SQL Server 2019+.  
> Handles millions of rows per job with zero downtime, background workers, and idempotent upserts via `acckey`.

**Highlights**
- 🚀 Background workers — long jobs run outside HTTP, safe from Cloudflare limits  
- 🧩 Batching with ROW_NUMBER() / OFFSET — handles multi-million-row tables  
- 🔁 Idempotent upserts — every document uses acckey as Elasticsearch _id  
- 💾 Job queue — file or SQL Server-based persistence  
- ⚖️ Retry logic + dead-letter queue for bad docs  
- 🧹 Normalization of dates, nulls, and diacritics  
- 📊 JSON logging for dashboards and traceability  

**Dashboards & KPIs**
| Fleet Dashboard | Sales KPI Dashboard |
|:--|:--|
| ![Fleet dashboard](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-dash-sc-1.png) | ![Sales KPI dashboard](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-dash-sc-2.png) |

**Elasticsearch Tables**
| Modules Reindex Table | Global Reindex Table |
|:--|:--|
| ![ES reindex modules](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-sc-1.png) | ![ES global reindex table](https://raw.githubusercontent.com/BRadivojevic/php-elasticsearch-reindex-workers/main/docs/elasticsearch-sc-3.png) |

---

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
Passionate about reliability, clean architecture, and automating the boring stuff.

📍 Belgrade, Serbia (UTC+1)  
📧 [b.radivojevic00@gmail.com](mailto:b.radivojevic00@gmail.com)  
🔗 [LinkedIn](https://linkedin.com/in/bosko-radivojevic-94a783238)
