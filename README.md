<!-- Banner / Greeting -->
<h1 align="center">Hi, I'm Swastik 👋</h1>

<p align="center">
  <b>CS @ Chitkara University • HackIndia National Champion • Researcher</b><br/>
  I engineer high-scale backends and research the math behind machine learning.
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=java,javascript,typescript,python,express,react,nextjs,tailwind,aws,docker,mongodb,mysql,postgres,git,linux" alt="skills" />
</p>

---

## 👨‍💻 About Me

- 🎓 **CS Undergrad** at Chitkara University, Punjab
- 🥇 **HackIndia 2024 National Champion** (1 of 2,839) · **ICIDEA '25** researcher (under review)
- 🛠 Building analytics platforms, fitness apps, SDE prep tools, and Web3 systems that ship to production
- 🔬 Applied ML researcher focused on energy systems and load forecasting
- 🌐 **Open to:** new engineering partnerships and full-time opportunities

---

## 🛠️ Tech Stack

- **Languages:** Java, JavaScript, TypeScript, Python, SQL
- **Backend:** Spring Boot, Express.js, Node.js, REST APIs, Microservices
- **Frontend/UI:** React.js, Next.js (App Router), Tailwind CSS
- **Cloud & DevOps:** AWS (EC2, S3), Docker, Linux CLI, GitHub Actions
- **Databases:** PostgreSQL (incl. Neon serverless), MongoDB, MySQL, Prisma ORM
- **ML / Data:** scikit-learn, Ridge regression, feature engineering
- **Auth & Tooling:** JWT, Clerk, Git, Postman, Bash

---

## 🚀 Featured Projects

### 🧮 **Codeforces Analytics Engine**
*Distributed analytics platform that turns raw Codeforces history into real-time, high-performance insights.*

- **🎯 Motivation:** Competitive programmers' Codeforces data is locked behind a rate-limited, Cloudflare-fronted API (~5 req/s/IP), making live dashboards slow and brittle. Existing tools re-fetch on every page load.
- **✅ Solution:** Decoupled sync architecture — a worker job queue (PostgreSQL-backed) pre-computes per-handle stats; the dashboard reads pre-aggregated rows for sub-second loads. Supports multi-handle linking, rating & tag-mastery overlays, peer comparison, and contest history.
- **📈 Impact:** Sub-second dashboard reads even with full contest history; designed to scale by distributing workers across distinct egress IPs to multiply API throughput.
- **🧰 Stack:** Next.js 16, React 19, Node.js 22, Express 5, PostgreSQL (Neon), Prisma 6, Docker, AWS EC2, JWT
- 🔗 **Repo:** https://github.com/Swastik2740S/CODEFORCES_API
- 🌐 **Live:** https://codeforces-api-rho.vercel.app/auth

---

### 💪 **SwastikFit — AI-Powered Body Recomposition**
*Multi-user fitness tracker: TDEE-calibrated macros, 6-day PPL program, progressive-overload logging.*

- **🎯 Motivation:** Generic fitness apps give every user the same 2,000 kcal plan and ignore equipment, experience, or diet. Lifters either stall on no-progress programs or juggle five separate apps.
- **✅ Solution:** 5-step onboarding → TDEE (Mifflin-St Jeor) + activity multiplier → personalised macros and meal plan respecting eggetarian/vegan/high-protein/low-carb preferences → 6-day Push/Pull/Legs program with auto-regeneration → progressive-overload engine that suggests `+2.5 kg` when rep targets are met. Food search via Edamam with 30-day cache, 7-day backfill for food/steps/weight, timezone-correct "today."
- **📈 Impact:** A full plan (macros + 6-day program + 100+ foods) generated in one onboarding flow; macro rings, streaks, and weekly adherence reports keep users accountable.
- **🧰 Stack:** Next.js 16, React 19, TypeScript, Clerk, PostgreSQL (Neon), Prisma 7, Edamam API, Zod, Framer Motion
- 🔗 **Repo:** https://github.com/Swastik2740S/personal_fit
- 🌐 **Live:** https://personal-fit-nu.vercel.app

---

### 📋 **PrepTrack — SDE Interview Preparation Tracker**
*Personal, single-user dashboard for DSA, System Design, and Behavioral prep against a one-year plan.*

- **🎯 Motivation:** SDE candidates juggle Striver A2Z (474 problems), GoF patterns, SOLID, HLD/LLD, and Amazon-style STAR stories across scattered spreadsheets — no single source of truth for "where am I in my prep?" Cloud-based trackers fail offline or during commutes; spreadsheets don't show streaks or pace.
- **✅ Solution:** A local-first dashboard tracking **DSA (Striver A2Z, 474 problems: E152/M186/H136)**, **System Design (GoF patterns, SOLID, refactoring, HLD, LLD)**, and **Behavioral (Amazon LP STAR stories)** against a one-year plan — with a **streak heatmap** and **on-pace indicator**. State lives in `localStorage` under key `preptrack-v1`; the app is fully offline-capable and zero-setup. Optional email magic-link sign-in enables cross-device sync via Supabase (Postgres + RLS + Realtime), moving only the diff from the seed in indexed deltas — single-digit KB per user.
- **📈 Impact:** A 474-problem catalog ships in the bundle, so syncing never uploads the catalog itself. Realtime edits stream across devices in ~1s under RLS isolation. PWA-installable, works offline once visited (service-worker caches the shell), and ships with a backup/restore flow that nags every 7 days. Test seed asserts `474 problems, 191 done, E152/M186/H136`.
- **🧰 Stack:** Next.js (App Router), TypeScript, Tailwind CSS, Zustand + persist, optional Supabase (Postgres + Auth + Realtime + RLS), PWA service worker
- 🔗 **Repo:** https://github.com/Swastik2740S/Tracker
- 🌐 **Live:** https://tracker-nine-lovat.vercel.app

---

### 🛰️ **Space Data Integrity Node** *(Bitcoin 2025 · exSat Track)*
*Decentralised, cryptographically verifiable storage for mission-critical space data.*

- **🎯 Motivation:** Space missions generate petabytes of sensitive data that must remain tamper-proof across multi-decade missions and distributed international teams. Centralised storage is a single point of failure and lacks verifiable integrity.
- **✅ Solution:** Files are encrypted client-side (AES-256-GCM via Web Crypto API) before they leave the device → uploaded to Pinata IPFS for redundant global storage → content hash anchored on the ExSat Testnet smart contract with multi-chain verification via Bitcoin OP_RETURN. Includes zero-knowledge proofs (verify existence without exposing content) and is tuned for high-latency deep-space communication. Aligned with NASA CRS-2 data integrity standards.
- **📈 Impact:** Tamper-evident storage with cryptographic proof of existence — anyone can verify a record on-chain, but only authorised users can decrypt the underlying file. Conference-selected at Bitcoin 2025.
- **🧰 Stack:** Next.js 14, Ethers.js, ExSat Testnet, Pinata IPFS (Filecoin), Web Crypto API, Hardhat, GitHub Actions
- 🔗 **Repo:** https://github.com/khushsharma509/Immutable-Data-Integrity-Solutions-for-Space-Exploration
- 🌐 **Live:** https://immutable-data-integrity-solutions-for-space-exploration.vercel.app

---

### 🌳 **Green Credit Marketplace** *(HackIndia 2024 — 1st / 2,839)*
*Web3-based marketplace for tokenised green credit trading on Ethereum.*

- **🎯 Motivation:** Carbon-offset / green-credit markets are opaque, with no transparent provenance, high intermediary fees, and weak audit trails. Buyers and sellers can't verify what they're trading.
- **✅ Solution:** MetaMask-based onboarding for users → browse tokenised green credits → purchases execute on Ethereum for immutable, on-chain provenance. Built end-to-end in 24 hours during HackIndia 2024.
- **📈 Impact:** Won HackIndia 2024 Web3 Track nationally out of 2,839 teams. Demoed end-to-end on-chain credit purchase with transparent transaction history.
- **🧰 Stack:** MERN (MongoDB, Express.js, React, Node.js), Solidity, Web3.js, Ethereum, MetaMask
- 🔗 **Repo:** https://github.com/khushsharma509/HackIndia-Spark-4---Supersqaud
- 🌐 **Live:** https://anothertry-delta.vercel.app
- 🎥 **Demo / Certificate:** https://drive.google.com/file/d/1i8qhs4xzMuPRaKeRbYLBJ3ZBYdwktF2p/view
- 📰 **LinkedIn Post:** https://www.linkedin.com/posts/hackindiaxyz_hackindia2024-hackindia2024-hackathon-activity-7260259500111114240-y2pZ

---

### 📝 **SmartTask — Task & Team Management System**
*Scalable, role-based collaboration with cloud-native deployment.*

- **🎯 Motivation:** Teams need a centralised system for users, projects, teams, and tasks with role-based access control — most off-the-shelf tools either oversimplify permissions or become unwieldy as teams grow.
- **✅ Solution:** Spring Boot 3.5 backend with five-tier RBAC (Admin → Project Manager → Team Lead → Member → Viewer), JWT auth with BCrypt hashing, full CRUD across projects/teams/tasks, and a Next.js frontend. Documented via Swagger/OpenAPI, deployed to AWS EC2 via Docker.
- **📈 Impact:** Handles 30 requests/second on cloud-deployed infrastructure; production-grade security and audit-ready API surface.
- **🧰 Stack:** Spring Boot 3.5, Spring Security, JWT, PostgreSQL, Next.js 13, Tailwind, Docker, AWS EC2, Swagger/OpenAPI
- 🔗 **Repo:** https://github.com/Swastik2740S/SmartTask

---

### 👔 **NesusHR — Employee Management System**
*Relational backend for complex organisational hierarchies and timesheet workflows.*

- **🎯 Motivation:** HR systems with multi-level reporting (employees → skip-level managers) and weekly timesheet approval workflows are typically locked behind enterprise SaaS — there's no clean, open-source backend for educational/startup use.
- **✅ Solution:** Express + Prisma + PostgreSQL backend modelling users, roles, departments, positions, employees (with reporting + skip-level managers), and timesheets (daily + weekly) with approval workflow. JWT auth with role-based middleware (Super Admin, Sub Admin, Employee).
- **📈 Impact:** Production-shaped HR data model with soft-delete and activation toggles, suitable as a foundation for real HR systems.
- **🧰 Stack:** Node.js, Express.js, Prisma ORM, PostgreSQL, JWT
- 🔗 **Repo:** https://github.com/divanshu-g/Employee-Management-System

---

### 💼 **Portfolio Website**
*Personal portfolio built with Next.js and deployed on Vercel.*

- 🌐 **Live:** https://swastikverma.in

---

## 🔬 Research

### ⚡ **Structural Shift in Peak Power Demand — Delhi Grid (2020–2025)**
*Under review · ICIDEA*

- **🎯 Motivation:** Standard load models treat weather as a linear covariate, which hides interaction effects — particularly the "Cooling Trap" where rising humidity amplifies cooling load non-linearly.
- **✅ Solution:** Modelled peak-demand growth via a **Heat × Humidity interaction term** (not weather as a linear covariate), capturing the "Cooling Trap" effect. Trained a **RidgeCV** regression on 12 years of Delhi grid data.
- **📈 Impact:** Peak load predicted at **R² 0.96 (train) / 0.93 (2024 hold-out)** with **RMSE 372 MW**. Quantified nocturnal load divergence to motivate battery-storage deployment.
- 🧠 **Methods:** RidgeCV regression, interaction-term feature engineering, time-based hold-out validation

---

## 🏆 Achievements

- 🥇 **National Champion** — HackIndia 2024, Web3 Track (1 of 2,839)
- 🚀 **Conference Showcase Selection** — Bitcoin 2025 · exSat Track
- 🔬 **Researcher (Under Review)** — *Structural Shift in Peak Power Demand — Delhi Grid (2020–2025)*, ICIDEA
- 🏅 **National Round Finalist** — HackFest 2024 · SAP × PSG iTech (Top 3 of 200+)
- 💻 **200+ LeetCode** problems solved in Java
- 🏅 **IEEE Core Member** — organized 6+ technical events

---

## 🎯 Interests

**Web3 & Blockchain** · **Distributed Systems** · **Applied ML** · **Hackathons**

---

## 🌍 Let's Connect

<p align="left">
  <a href="mailto:onamverma8@gmail.com"><img src="https://img.shields.io/badge/email-333333?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/swastik-verma-153b30253/"><img src="https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://github.com/Swastik2740S"><img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://leetcode.com/u/swastik2740s/"><img src="https://img.shields.io/badge/leetcode-FFA116?style=for-the-badge&logo=leetcode&logoColor=white" /></a>
  <a href="https://swastikverma.in"><img src="https://img.shields.io/badge/portfolio-333333?style=for-the-badge&logo=vercel&logoColor=white" /></a>
</p>

---

## 📊 GitHub Analytics
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Swastik2740S&theme=github-dark&area=true&color=00AEEF&line=00AEEF&hide_border=true" />
</p>

---

## 🐍 Contribution Snake

<p align="center">
  <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg" />
</p>

---

<p align="center">
  <i>Thanks for visiting! Feel free to connect 💙</i>
</p>
