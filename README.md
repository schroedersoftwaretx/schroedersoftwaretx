<h1 align="center">Sean O'Toole</h1>

<p align="center">
  <a href="https://github.com/schroedersoftwaretx"><img src="https://img.shields.io/github/followers/schroedersoftwaretx?label=Follow&style=social" alt="GitHub followers"></a>
  <a href="https://www.linkedin.com/in/seanotoole04/"><img src="https://img.shields.io/badge/LinkedIn-Connect-blue" alt="LinkedIn"></a>
  <a href="https://schroedersoftware.com/"><img src="https://img.shields.io/badge/Portfolio-Visit-orange" alt="Portfolio"></a>
</p>

## 📊 Software & Data Engineer | Decision Systems Under Uncertainty

I build complete systems rather than isolated analyses — data ingestion through modeling, backend, frontend and deployment. The thread running through most of my work is **quantifying decision quality under uncertainty with correct handling of time**: point-in-time snapshots that prevent look-ahead bias, immutable source data with everything downstream derived, and valuation measured against the next-best alternative.

Currently completing a **Master in Business Analytics and Data Science at IE University** in Madrid, after a B.S. in Computer Science (Highest Honors, Mathematics minor) from UTSA.

### 🔍 Focus Areas

* **Data Engineering:** ETL pipeline design, parallel ingestion, data quality validation, entity resolution, warehouse modeling.
* **Quantitative Modeling:** Valuation curves, Monte Carlo simulation over future states, replacement-level baselines, point-in-time backtesting.
* **Full-Stack Engineering:** TypeScript/Next.js and Python services over PostgreSQL, with migrations, CI and real integration tests.
* **Applied ML & LLM Systems:** RAG pipelines, hybrid retrieval with reranking, LLM output evaluation against labeled ground truth.

### 🛠️ Technical Toolkit

* **Languages:** Python, TypeScript, SQL, Java, JavaScript, PHP, R
* **Data & Storage:** PostgreSQL, MySQL, SQLite, Parquet, Firebase, Drizzle ORM, schema design & migrations
* **Modeling:** pandas, NumPy, scipy, scikit-learn, isotonic regression, K-means, Monte Carlo simulation
* **Infrastructure:** AWS EC2, Vercel, Docker, Nginx, Linux, GitHub Actions
* **Testing:** Vitest, Testcontainers, Playwright, JUnit, golden-file regression testing

---

## 🔬 Projects

### ⚽ World Cup Fantasy — full-stack valuation and scoring platform
`TypeScript` `Next.js` `React` `PostgreSQL` `Drizzle` `Vitest`

A draft-based fantasy platform for the 2026 World Cup, built solo in about seven weeks. ~53,000 lines of TypeScript across a framework-agnostic domain layer, 39 Postgres tables, 22 hand-written idempotent migrations and 51 API routes.

* **Immutable source, derived everything.** Stat lines are append-only and never mutated; standings, head-to-head results and awards are pure functions computed on read. Re-ingesting one corrected record restates every dependent number — there is no cache-invalidation logic in the codebase because there is nothing to invalidate.
* **Content-hashed scoring rulesets**, so structurally identical rule sets share an ID and any point-value change yields a new one. Enables what-if scoring under an alternate ruleset without touching the canonical numbers.
* **518 tests** across unit, integration (Testcontainers-managed Postgres running real migrations) and component tiers, gated in GitHub Actions CI across three parallel jobs.

### 📉 Draft Analytics Engine — statistical valuation and live decision support
`Python` `scikit-learn` `scipy` `pandas` `SQLite`

An end-to-end analytics system: reverse-engineered data ingestion, a normalized warehouse, and a five-layer recommendation engine.

* **Isotonic regression for the price-to-value curve.** Linear, logarithmic, quadratic and cubic fits all failed to capture its shape — the relationship is monotonic but not parametric. The residual against the monotonic fit became the mispricing signal.
* **Monte Carlo opportunity cost.** Each asset's market price is treated as a distribution; 50 seeded simulations per evaluation estimate which assets survive to the next decision point.
* **Explainable by construction** — every recommendation emits its full signal breakdown, per-layer scores and a generated natural-language rationale.

### 🎯 Underdog Draft Analytics Platform — point-in-time decision grading
`TypeScript` `React` `Vite` `Python` `pandas` `Parquet`

* **Eliminated look-ahead bias** by freezing a projection snapshot at the moment each decision was made, so historical decisions are scored only against information that existed then. This is the same discipline as point-in-time data in financial backtesting.
* **One pure engine, two directions.** The evaluation core has no I/O and no side effects, so the same ranking functions serve both live forward recommendation and retrospective backward grading — no duplicated logic, no mode branch.
* **Self-maintaining statistical tiers** — tier breaks are detected wherever a gap exceeds μ + 1σ of the gap distribution, so tiers redraw themselves whenever projections change.

### 🗄️ High-Volume Ingestion Pipeline — 5.1M-row parallel ETL
`PHP` `MySQL` `AWS EC2` `POSIX`

* Partitioned a **405 MB / 5.1M-row** dataset into 52 chunks executed through a **hand-rolled POSIX process pool** with bounded concurrency, PID-based liveness reaping and per-chunk log isolation.
* **Typed data-quality layer** sorting every rejected row into one of 8 error categories with the raw offending line retained, and global line numbers reconstructed across parallel workers.
* **Self-instrumenting** — each worker writes rows processed, errors, elapsed time and throughput to a metrics table, so pipeline performance is measured rather than estimated.

### 🤖 AI Enterprise Data Assistant — natural-language access to internal data
`Python` `FastAPI` `React` `RAG` `Gemini` `Firebase`

* A local **RAG pipeline** grounding Gemini in internal company data via multi-stage query rewriting and **hybrid retrieval** (dense semantic + BM25 lexical) with a reranking stage.
* Decoupled microservices across separate repositories, with a local cache layer for chat history and Firebase for secure organizational storage.

---

## 📣 Let's Connect

* 🌐 [schroedersoftware.com](https://schroedersoftware.com/)
* 💼 [LinkedIn](https://www.linkedin.com/in/seanotoole04/)

---

## 📈 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=schroedersoftwaretx&show_icons=true" alt="Sean's GitHub stats">
</p>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=schroedersoftwaretx&layout=compact" alt="Top languages">
</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=schroedersoftwaretx&style=flat-square&color=orange" alt="Profile views">
</p>
