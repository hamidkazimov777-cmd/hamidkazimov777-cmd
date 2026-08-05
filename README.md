<div align="center">

# Hi, I'm Hamid 👋

**Full-stack developer — I build and ship complete products end-to-end**

[![Telegram](https://img.shields.io/badge/Telegram-@hamidkazimov-2CA5E0?style=flat-square&logo=telegram&logoColor=white)](https://t.me/hamidkazimov)
[![Email](https://img.shields.io/badge/Email-hamidkazimov777%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:hamidkazimov777@gmail.com)

</div>

---

## About

I design, build, and deploy full-stack products solo — from database schema to production VPS. My focus is Next.js/TypeScript applications with real infrastructure decisions behind them: auth flows that actually work end-to-end, background job pipelines, third-party API integrations, and legal/compliance requirements (data localization, terms of service) that most side projects skip.

I care about **shipping working software**, not portfolios of half-finished demos — every project below is live in production.

---

## Featured Projects

### 🎧 [ForzaDJ](https://github.com/hamidkazimov777-cmd/forzadj) — [Live →](https://forzadj.ru)
Free DJ-pool platform: catalog, streaming preview, downloads, editorial packs, personal crates. Full audio pipeline (BPM/key auto-detection via Essentia.js WASM, waveform generation, WebP artwork optimization), Telegram-only authentication, three-tier role system, and a donation-supported (no-subscription) business model.

`Next.js 15` `TypeScript` `Prisma` `PostgreSQL` `Tailwind v4` `Supabase Storage`

### 🤖 [ForzaDJ Admin Bot](https://github.com/hamidkazimov777-cmd/forzadj-admin-bot)
Telegram bot that publishes tracks to the ForzaDJ catalog from a single uploaded audio file — AI genre/mood classification (Groq Llama 3.3 70B), automatic metadata extraction with a three-level fallback chain, inline editing, and a secret-authenticated HTTP bridge to the main platform. Built with a pluggable AI-provider abstraction (7 interchangeable backends).

`grammY` `TypeScript` `Groq AI` `Node.js`

---

## What I've actually dealt with in production

Not textbook examples — real problems from running these projects live:

- Migrating a production Postgres database between providers with zero data loss, driven by a legal requirement (152-FZ data localization), not a whim
- Diagnosing an intermittent "empty JSON response" bug that only reproduced in production, traced to a stale pooled HTTP connection between two hosts — not a timeout, not encoding, a connection-reuse edge case
- Switching a Telegram bot from webhook to long-polling after discovering the hosting provider silently firewalls Telegram's IP ranges
- Writing Terms of Service / Privacy Policy documents that hold up under actual data-protection law, not boilerplate

---

## Stack

`TypeScript` · `Next.js` · `React` · `Node.js` · `PostgreSQL` · `Prisma` · `Tailwind CSS` · `Supabase` · `PM2` · `GitHub Actions`

---

<div align="center">

**Reach out:** [Telegram](https://t.me/hamidkazimov) · [Email](mailto:hamidkazimov777@gmail.com)

</div>
