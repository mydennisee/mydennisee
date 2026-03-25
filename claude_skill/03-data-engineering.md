# 03 — Data Engineering & Pipelines

## What I Do

Design and build scalable data pipelines that serve machine learning systems, analytics platforms, and business reporting. Work spans ETL/ELT design, feature store architecture, data modelling, and terabyte-scale processing on distributed compute.

---

## How I Approach It

### Pipeline Design
- Define the consumer first — what does the downstream ML model or dashboard need?
- Choose ETL vs. ELT based on transformation complexity and target platform
- Design for idempotency — every pipeline run should be safe to rerun
- Upsert patterns over inserts: prevent duplicates on reprocessing

### Data Modelling
- Dimensional modelling (star/snowflake) for analytics workloads
- SCD-2 (Slowly Changing Dimensions Type 2) for historical tracking — critical for temporal ML features
- Feature store design: one source of truth per feature, versioned, reusable across models
- Naming conventions enforced at schema level — not documentation

### Distributed Processing (PySpark / Hadoop)
- Partition strategy designed before writing any transformation logic
- Avoid wide shuffles — colocate joins where possible
- Cache intermediate DataFrames that are reused multiple times
- Broadcast small lookup tables to avoid shuffle joins
- Monitor skew — partition imbalance kills cluster utilisation

### SQL Optimisation
- Predicate pushdown — filter early, transform late
- CTE over nested subqueries for readability and plan optimisation
- Analyse query execution plans before declaring a query "done"
- Materialise intermediate results for complex multi-step transformations

### Data Quality
- Row counts, null rates, and value distributions checked at pipeline entry and exit
- Schema enforcement — no silent schema drift
- Reconciliation checks between source and target record counts
- Alerting on anomaly thresholds, not just failures

---

## Tools & Stack

| Category | Tools |
|----------|-------|
| Processing | PySpark, Apache Spark, Hadoop (HDFS/YARN) |
| Orchestration | Apache Airflow |
| Transformation | dbt, SQL, Python |
| Storage | Hive, PostgreSQL, Supabase, S3-compatible object stores |
| Acceleration | RAPIDS (GPU-accelerated data processing) |

---

## Demonstrated Work

- **Terabyte-scale ETL pipelines** — PySpark/Hadoop pipelines processing large-scale transactional data. Partition-aware design, broadcast joins, intermediate caching.
- **Feature store & SCD-2 design** — Historical feature tracking for time-windowed ML models. Single source of truth pattern across multiple scoring models.
- **FinDoc Intelligence — Storage layer** — Dual-write to PostgreSQL (structured KPIs) and pgvector (semantic embeddings). Upsert pattern for idempotent reprocessing.

---

## My Standard: What "Done" Looks Like

- Pipeline is idempotent — safe to rerun without side effects
- Row count and schema reconciliation checks at entry and exit
- No hardcoded dates or paths — fully parameterised
- Execution time benchmarked before and after optimisation
- Data lineage documented from source to model feature
