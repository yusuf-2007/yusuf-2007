<div align="center">

# Yusuf Nusratkhujaev

**Computer Science @ RIT** · Class of 2029 · Rochester, NY

*Building production software for a market most people don't build for.*

`Tashkent → Jeddah → Rochester` · `EN` `RU` `UZ` `AR`

</div>

---

Most of what I write ships to users in Uzbekistan — a market with 37 million people, three writing systems in daily use, and very little software built natively for it. That constraint shapes everything: payment rails that aren't Stripe, data-localization law that rules out US hosting, and search that has to handle a user typing Uzbek Latin, Uzbek Cyrillic, and Russian in the same sentence.

Most of my repositories are private. Here's the honest inventory.

---

## Currently building

### Mezon Ta'lim — certification learning platform
`Next.js` `self-hosted Supabase` `Docker` `PostgreSQL`

The first Uzbek-language platform for AAOIFI CPSS certification. Uzbek law requires citizen data to stay in-country, so this runs on self-hosted infrastructure in Tashkent rather than anything convenient.

<details>
<summary>What that actually involved</summary>

- Modular monolith architecture on self-hosted Supabase
- Four vendor integrations: Bunny.net Stream, Click and Payme for payments, Eskiz for SMS — contracts negotiated directly
- Data-localization research documented for non-technical stakeholders before a line of infrastructure was provisioned

</details>

### Mufeed — live course platform
`Next.js` `TypeScript` `Supabase` `Payme` `Vercel`

Live, running the full journey end to end: buy a course, take it, sit the exam, get the certificate. No manual step anywhere.

<details>
<summary>What that actually involved</summary>

- PostgreSQL schema and Row Level Security policies — the frontend queries the database directly, so authorization lives in the database rather than in code I have to remember to write
- Payme integration across the complete purchase-to-certificate flow
- Diagnosed and remediated a production database compromise: found injected rows through direct SQL inspection, purged them, verified integrity afterward

</details>

### Joytop — restaurant discovery, Tashkent *(team project)*
`React Native` `Next.js` `TypeScript` `PostgreSQL/PostGIS`

Context-aware restaurant search across a 2,000-venue catalog. My side is the ranking layer, mobile, and database.

<details>
<summary>What I own</summary>

- **The discovery ranking layer** — PostGIS functions doing occasion-based mood ranking, per-mood search radius with proximity weighting, and a demographic affinity prior. Replaced a flat price-sorted list.
- **A 9.5s → 400ms search fix** — an `EXISTS` probe was misleading the query planner into sequentially scanning 140K menu rows. The counterintuitive part: empty result sets were the *slow* case, because `EXISTS` has no first match to stop at.
- **Onboarding and auth** — taste capture, phone OTP and email sign-in, location priming, plus the backing profile schema
- 12 database migrations, and full localization across Uzbek, Russian, and English including Cyrillic/Latin code-switching
- An independent technical review of the AI integration architecture — RAG versus fine-tuning, grounding constraints, and cost ceilings against projected query volume

</details>

---

## Stack

| | |
|---|---|
| **Languages** | TypeScript · JavaScript · Python · Java · C · C++ · SQL |
| **Frontend** | Next.js · React · React Native (Expo) · Tailwind |
| **Data** | PostgreSQL · PostGIS · Supabase · schema design · query optimization · RLS |
| **Infra** | Docker · Vercel · self-hosted Linux · Git |
| **Learning** | Neural nets from scratch (Karpathy) · competitive programming in C++ |

---

## Before this

**Frontend Developer Intern @ Mohirlar** — summers 2023 and 2024. Built the production landing page for uzbekvoice.ai in React and TypeScript. Learned TypeScript from zero in under a month to meet the team's standards, then stayed on the primary client project.

**Mark-It Day 2025** — organized a campus fundraising event that raised over SAR 600,000 (~USD 160,000). Vendors, budget, volunteer teams, multi-month timeline.

---

<div align="center">

[LinkedIn](https://www.linkedin.com/in/yusuf-nusrat/) · yn6281@rit.edu

<sub>Happy to walk through architecture decisions or share code on request.</sub>

</div>
