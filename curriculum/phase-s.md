---
title: Phase S — Data Engineering
parent: Curriculum
nav_order: 15
---

# Phase S — Data Engineering

## Run This In Parallel From Day One

This phase is your professional lane. Start here alongside Phase 1 (UNIX) — you'll recognize patterns from daily work, and that recognition anchors the CS theory. Each section builds on your existing knowledge rather than replacing it.

---

## Connection to Core CS

| DE Pain Point | CS Foundation That Fixes It |
|--------------|----------------------------|
| Spark errors feel like voodoo | Phase 5 (OS): processes, memory, scheduling — Spark *is* a distributed OS |
| Slow queries, can't read EXPLAIN | Phase 8 (Databases): B-trees, paging, execution plans |
| Kafka consumer groups confusing | Phase 7 (Networking): TCP, connections, message passing |
| Pipeline failures hard to debug | Phase 1 (UNIX): `strace`, `lsof`, `journalctl` |
| Don't understand column formats | Phase 3 (C): memory layout, alignment, how data sits in bytes |

---

## S-1 — Foundations

<details open>
<summary><strong>🎯 Layer 0 — Must Read</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| **Designing Data-Intensive Applications (Kleppmann)** | The most important book for your career. Covers distributed systems, databases, streaming, consistency — everything DE touches. | [→ free PDF](https://github.com/ms2ag16/Books/blob/master/Designing%20Data-Intensive%20Applications.pdf) |
| Data Engineer Handbook | Breadth-first DE reference | [→](https://github.com/DataExpert-io/data-engineer-handbook) |

**Read DDIA in this order:** Ch 1–3 (foundations) → Ch 5–6 (replication/partitioning) → Ch 10–11 (batch/streaming) → Ch 7–9 (transactions) for depth.

</details>

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

- [Fundamentals of Data Engineering — Joe Reis talk](https://www.youtube.com/watch?v=PdWzRqCT_Zo)
- [Awesome Data Engineering curated list](https://github.com/igorbarinov/awesome-data-engineering)

</details>

---

## S-2 — SQL Mastery

<details open>
<summary><strong>🎯 Layer 0 — Must Do</strong></summary>

SQL is not a simple language. Window functions, CTEs, recursive queries, and query planning are skills you use every day but may never have studied systematically.

| Resource | Why | Link |
|----------|-----|------|
| Use The Index, Luke | The best free resource on SQL performance that exists. Explains B-tree indexes, execution plans, why queries are slow. | [→](https://use-the-index-luke.com/) |
| pgexercises.com | Free, browser-based, graded SQL exercises — no registration | [→](https://pgexercises.com/) |
| Mode SQL Tutorial — Advanced SQL | Window functions, subqueries, performance | [→](https://mode.com/sql-tutorial/intro-to-advanced-sql/) |

**Practice sequence:** pgexercises Basics → Aggregates → Joins → **Window functions (do all of these)** → Recursive

</details>

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| PostgreSQL EXPLAIN documentation | How to read query plans in detail | [→](https://www.postgresql.org/docs/current/using-explain.html) |
| `EXPLAIN ANALYZE` on your real queries | Do this at work. Run `EXPLAIN (ANALYZE, BUFFERS)` on a slow query and understand every line. | — |
| Markus Winand's talks | "Modern SQL" — what SQL:2003+ features you should be using | [→](https://www.youtube.com/@MarkusWinand) |

</details>

---

## S-3 — Spark & Databricks

**This section addresses the "Spark errors are voodoo" problem directly.** The root cause is always the same: optimizing Spark requires understanding its *execution model*, not just the DataFrame API.

<details open>
<summary><strong>🎯 Layer 0 — Execution Model First</strong></summary>

Before any Spark "tips", you need to understand how Spark actually runs your code:

| Concept | Why It Matters |
|---------|---------------|
| **DAG → stages → tasks** | Every action triggers a DAG. Stages are divided at shuffle boundaries. Tasks are the actual units of work. |
| **Partitions** | Your DataFrame has N partitions. Each task processes one partition. Too few = underutilized. Too many = overhead. |
| **Shuffles** | The expensive part. Any `groupBy`, `join`, `repartition` moves data across the network. This is where most Spark slowness lives. |
| **Catalyst Optimizer** | Spark rewrites your logical plan before executing. Understanding this explains why some "obvious" optimizations don't help. |
| **Broadcast joins** | When one side is small enough, skip the shuffle entirely. `broadcast()` hint or auto-broadcast threshold. |

| Resource | Link |
|----------|------|
| Mastering Apache Spark (Jacek Laskowski) — free gitbook | [→](https://books.japila.pl/apache-spark-internals/) |
| Spark: The Definitive Guide — free chapters (O'Reilly) | [→](https://www.oreilly.com/library/view/spark-the-definitive/9781491912201/) |
| Databricks Academy — free tier | [→](https://www.databricks.com/learn/training/home) |
| Spark UI walkthrough (Databricks blog) | [→](https://www.databricks.com/blog/2015/06/22/understanding-your-spark-application-through-visualization.html) |

</details>

<details>
<summary><strong>📖 Layer 1 — Optimization Patterns</strong></summary>

**The 5 most common PySpark performance problems (and fixes):**

| Problem | Symptom | Fix |
|---------|---------|-----|
| **Too many small files** | Slow reads, many tasks | `coalesce()` before write, or tune `spark.sql.files.maxPartitionBytes` |
| **Data skew** | One task takes 10× longer | Salting, `skewHint`, or AQE (Adaptive Query Execution) |
| **Unnecessary shuffle** | Slow `groupBy` / `join` | Broadcast smaller side, pre-partition on join key, use `repartition` strategically |
| **UDFs killing performance** | Catalyst can't optimize them | Rewrite as native Spark functions where possible; use Pandas UDFs over row UDFs |
| **Missing partition pruning** | Reading entire table | Filter on partition column *before* any joins; verify with EXPLAIN |

```python
# Read the execution plan — do this every time you write a slow query
df.explain(mode="formatted")   # Shows logical + physical plan
df.explain(mode="cost")        # Shows cost estimates

# Adaptive Query Execution (Spark 3+) — enable if not on by default
spark.conf.set("spark.sql.adaptive.enabled", "true")
spark.conf.set("spark.sql.adaptive.coalescePartitions.enabled", "true")
```

| Resource | Link |
|----------|------|
| Spark Performance Tuning (official docs) | [→](https://spark.apache.org/docs/latest/sql-performance-tuning.html) |
| AQE explained (Databricks blog) | [→](https://www.databricks.com/blog/2020/05/29/adaptive-query-execution-speeding-up-spark-sql-at-runtime.html) |
| Delta Lake optimization guide | [→](https://docs.delta.io/latest/optimizations-oss.html) |

</details>

<details>
<summary><strong>🔬 Layer 2 — Databricks-Specific</strong></summary>

| Topic | Resource |
|-------|----------|
| Photon engine (Databricks runtime) | [Databricks docs: Photon](https://docs.databricks.com/runtime/photon.html) |
| Unity Catalog + data governance | [Databricks docs: Unity Catalog](https://docs.databricks.com/data-governance/unity-catalog/index.html) |
| Cluster configuration (worker type, autoscaling) | [Databricks docs: Cluster configuration](https://docs.databricks.com/clusters/configure.html) |
| `%python` vs `%sql` cell performance | Avoid switching back and forth in notebooks; SparkSession overhead |

</details>

<details>
<summary><strong>📺 Layer 3 — Big Series</strong></summary>

- [DataTalksClub DE Zoomcamp lectures](https://www.youtube.com/playlist?list=PL3MmuxUbc_hJed7dXYoJw8DoCuVHhGEQb)
- [Advancing Spark — YouTube channel](https://www.youtube.com/@advancingspark) — deep Spark internals
- [Apache Spark Summit talks (YouTube)](https://www.youtube.com/c/SparkSummit) — real-world optimization war stories

</details>

---

## S-4 — Data Modeling & dbt

<details open>
<summary><strong>🎯 Layer 0 — Must Know</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| dbt Learn — free courses | Hands-on dbt from the source, browser-based | [→](https://courses.getdbt.com/) |
| The Data Warehouse Toolkit (Kimball) — key chapters | Dimensional modeling: facts, dimensions, slowly changing dimensions | [→](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/books/data-warehouse-dw-toolkit/) |
| dbt documentation fundamentals | Sources, models, tests, macros | [→](https://docs.getdbt.com/docs/introduction) |

</details>

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Topic | Resource |
|-------|----------|
| Data Vault 2.0 | Alternative to Kimball for enterprise DW | [→](https://datavaultalliance.com/learn/) |
| dbt advanced features | Snapshots, incremental models, macros | [→](https://docs.getdbt.com/docs/build/incremental-models) |
| Analytics Engineering with dbt (free book) | Community-maintained, practical | [→](https://www.getdbt.com/analytics-engineering/) |

</details>

---

## S-5 — Streaming & Kafka

<details open>
<summary><strong>🎯 Layer 0 — Must Understand</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Kafka in 100 seconds (Fireship) | Best 2-minute explanation of what Kafka is | [→](https://www.youtube.com/watch?v=uvb00oaa3k8) |
| Confluent Kafka 101 — free course | Free, browser-based, official | [→](https://developer.confluent.io/courses/apache-kafka/events/) |
| DDIA Ch 11 — Stream Processing | The theory: why streaming, when batch vs stream | Part of your DDIA reading |

| Concept | What It Means for You |
|---------|----------------------|
| **Topics + partitions** | Like a distributed, ordered queue. Partitions = parallelism. |
| **Consumer groups** | Multiple consumers on same topic — each partition goes to one consumer in the group. |
| **Offset** | Where a consumer is in a partition. Commit offset = acknowledge processed. |
| **Log compaction** | Kafka keeps the latest value per key. Useful for CDC / state topics. |

</details>

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

- Apache Flink or Spark Structured Streaming for stateful stream processing
- [Kafka Connect for data pipeline integration](https://docs.confluent.io/platform/current/connect/index.html)
- [Kafka Streams for lightweight stream processing in JVM](https://kafka.apache.org/documentation/streams/)

</details>

---

## 🏗 Project

- **Data Engineering Zoomcamp** — free, structured, hands-on across all DE topics [→](https://github.com/DataTalksClub/data-engineering-zoomcamp)
- Start at Module 3 (Data Warehouse / BigQuery) if Modules 1–2 feel like revision

---

## Done when...

You can look at a Spark UI, identify which stage is causing slowness, state the reason (shuffle, skew, too many partitions, missing broadcast), and apply the correct fix without guessing.
