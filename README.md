# Performance Engineering Lab

**Reproduce. Diagnose. Fix. Benchmark. Share.**

A public collection of reproducible application performance incidents — real problems, real investigations, real tools, real evidence.

> If you encounter a performance problem, you shouldn't always have to start your investigation from scratch. Find a related incident here, learn from the investigation, reproduce it, use the provided tools, and validate the solution with evidence.

This is **not** a monitoring tool, a magic fix generator, or a production troubleshooting agent. It's a knowledge base + reproducible lab + practical reference to help you get started faster.

---

## Why This Exists

When you hit a performance problem, you often don't know where to start: what to measure, which tools to use, what commands to run, or how to isolate the root cause. Most developers end up re-doing the same research from scratch, every time.

This repository collects real performance incidents — each one reproducible, diagnosed, fixed, and benchmarked — so you can search for something similar to what you're facing and skip straight to a working starting point.

```text
Performance Problem
        ↓
Search this repository
        ↓
Find a related incident
        ↓
Read the investigation
        ↓
Use the provided tools
        ↓
Reproduce the problem
        ↓
Understand the root cause
        ↓
Try the documented fix
        ↓
Run the benchmark
        ↓
Compare Before vs After
```

This project is **technology-agnostic in scope**. It covers application performance broadly — APIs, databases, ORMs, caching, JVM/memory, concurrency, connection pools, messaging (Kafka/RabbitMQ), external latency, network bottlenecks, distributed systems, observability, and load testing. It's not a database-only or Java-only project — those are simply where the current examples live.

---

## Repository Structure

```text
performance-engineering-lab/
│
├── README.md
│
├── incidents/            # Individual, self-contained performance incidents
│   ├── database/
│   │   ├── 001-missing-composite-index/
│   │   ├── 002-full-table-scan/
│   │   └── 003-deadlock/
│   ├── hibernate/
│   │   └── 001-n-plus-one/
│   ├── redis/
│   └── api/
│
├── workloads/            # Reusable sample apps/datasets used to reproduce incidents
│   └── stock-research/
│       ├── src/
│       ├── database/
│       ├── tools/
│       └── docker-compose.yml
│
├── load-testing/         # Reusable load-testing setups
│   ├── k6/
│   └── jmeter/
│
├── observability/        # Monitoring/observability configs
│   ├── prometheus/
│   └── grafana/
│
├── docs/                 # Project-wide documentation
│   ├── architecture.md
│   ├── contribution-guide.md
│   └── performance-methodology.md
│
└── .github/
    ├── ISSUE_TEMPLATE/
    └── pull_request_template.md
```

### `incidents/`
Each incident is self-contained and includes its own `README.md`, problem description, reproduction steps, diagnostics, fix, load test, and before/after results. The incident's README is the main entry point — open it and you'll find the full story: what happened, why, how it was investigated, what fixed it, and how the fix was proven. Incidents are grouped by area (database, hibernate, redis, api, ...) and numbered within each area as they're added.

### `workloads/`
Reusable sample applications and datasets used to reproduce incidents realistically. Each workload is self-contained, with its own source, database setup, tools, and runtime files (`src/`, `database/`, `tools/`, `docker-compose.yml`). The initial workload is a **Stock Research Platform**, used purely as a vehicle to reproduce realistic problems — this is not a stock-market project. Future workloads may cover e-commerce, payments, banking, logistics, or other domains.

### `load-testing/`
Reusable load-testing scenarios (K6, JMeter) used to generate realistic traffic and measure performance before and after a fix.

### `observability/`
Monitoring and observability configuration (Prometheus, Grafana, JVM/app/infra metrics) used to gather diagnostic evidence during investigations.

### `docs/`
Project-wide documentation: performance methodology, architecture notes, and contribution guidelines.

---

## Standard Incident Structure

Every incident follows the same structure, so once you know one, you know them all:

```text
Incident
   │
   ├── 1. Scenario
   ├── 2. Symptoms
   ├── 3. Reproduction
   ├── 4. Baseline
   ├── 5. Investigation
   ├── 6. Root Cause
   ├── 7. Solution
   ├── 8. Validation
   ├── 9. Before vs After
   └── 10. Lessons Learned
```

**No optimization without evidence.** Every solution must be backed by measurable data — latency, throughput, error rate, CPU, memory, query count, cache hit rate, thread utilization, queue depth, or load-test results.

---

## Using This Repository

1. Identify the symptom you're seeing.
2. Search the repository for a similar incident.
3. Open the incident's README.
4. Review the investigation and diagnostic tools used.
5. Reproduce the scenario locally, where possible.
6. Follow or adapt the documented investigation approach.
7. Apply or adapt the documented solution.
8. Run the validation/benchmark.
9. Compare before vs after results.
10. Use the findings to guide your own investigation.

The goal is to help you **start faster**, not to hand you a guaranteed fix.

---

## Why Public?

Performance investigations tend to involve the same repeated research and trial-and-error, over and over, across different teams and companies. Making these investigations public turns that repeated effort into a shared, searchable knowledge base.

This project aims to:

- Share practical, real performance investigations
- Make diagnostic approaches reusable
- Provide reproducible examples
- Help developers discover useful tools
- Reduce duplicated investigation effort
- Encourage engineers to contribute their own incidents

---

## Contributing

New incidents are welcome. A good contribution follows the [standard incident structure](#standard-incident-structure) — scenario, symptoms, reproduction, baseline, investigation, root cause, solution, validation, before/after, lessons learned.

Reproducible evidence — commands, scripts, configs, metrics — is more valuable than narrative alone. Use the templates in [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) and [`.github/pull_request_template.md`](.github/pull_request_template.md), and see [`docs/contribution-guide.md`](docs/contribution-guide.md) for details.

---

## Current Technology Examples

Current incidents happen to use: Java, Spring Boot, Hibernate/JPA, MySQL, K6, JMeter, Prometheus, Grafana, and Docker.

The repository itself is **not tied to these technologies** — future incidents can introduce any stack.

---

**Reproduce. Diagnose. Fix. Benchmark. Share.**