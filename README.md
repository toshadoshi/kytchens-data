# Kytchens — Data Architecture

Internal data architecture documentation for Kytchens, a multi-brand cloud kitchen operator running 25+ kitchens and 45+ food brands across Mumbai and Pune.

## Documents

| File | Description |
|------|-------------|
| `index.html` | Full 9-page architecture document — sources, pipeline layers, all table definitions, ID maps, golden rules, KPI reference |
| `summary.html` | 2-page executive summary — the problem, what exists, what's broken, what needs building, table reference grid |

## What This Covers

- **7 data sources** — UrbanPiper (orders), SupplyNote (inventory), Bravery (photo evidence), Restaverse (complaints), Keka (people), Tally (finance), POS/manual sales
- **5-layer pipeline** — Raw → Staging → Mart → Analytics → Semantic
- **18 core tables** with full column definitions
- **ID naming convention** — resolving up_order_id vs aggregator_order_id vs quint_id across all sources
- **KPI formulas** — GMV, NMV, KPT, complaint rate, kitchen error rate, OOS, settlement calculation
- **Golden rules** for pipeline design

## Stack

- **ClickHouse** (AWS) — order analytics, 177M+ rows
- **Supabase** (Postgres, Mumbai) — operational layer for new modules
- **Target:** ClickHouse + Supabase unified through a Semantic layer for the Kitchen Intelligence AI agent

---

*Confidential — Internal use only · April 2026*
