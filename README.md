<div align="center">

# Yusuf Nusratkhujaev

**Computer Science @ RIT** · Class of 2029 · Rochester, NY

*I build web and mobile apps for people in Uzbekistan, where I'm from.*

`Uzbekistan → Jeddah → New York` · `EN` `RU` `UZ` `AR`

</div>

---

Very little software is made with Uzbek users in mind, so building for them means solving problems most tutorials skip:

- **Payments:** Stripe doesn't work there, so checkout runs on local providers like Payme and Click.
- **Hosting:** Uzbek law requires citizens' personal data to stay inside the country, so some of my apps run on servers in Tashkent instead of AWS or Vercel.
- **Language:** people type in Uzbek (in both Latin and Cyrillic letters) and in Russian, sometimes in the same search, so search and the UI have to handle all of it.

Most of my repositories are private, so here's what I've built and what I actually did on each.

---

## Currently building

### [Mufeed](https://mufeed.uz) · online courses in Islamic finance
`Next.js` `TypeScript` `Supabase` `Payme` `Vercel`

A live course platform in Uzbek. Students buy a course, take it, sit the exam, and get their certificate, with no manual step anywhere.

<details>
<summary><b>What that actually involved</b></summary>

- PostgreSQL schema and Row Level Security policies. The frontend queries the database directly, so authorization lives in the database rather than in code I have to remember to write.
- Payme integration across the complete purchase-to-certificate flow
- Diagnosed and fixed a production database compromise: found injected rows through direct SQL inspection, purged them, and verified integrity afterward

</details>

### [Mezon Ta'lim](https://mezon-talim.vercel.app) · certification prep platform *(launching soon)*
`Next.js` `self-hosted Supabase` `Docker` `PostgreSQL`

The first platform in Uzbek for AAOIFI's CPSS certification, a professional credential in Islamic finance. Because of Uzbekistan's data localization law, it runs on self-hosted infrastructure in Tashkent rather than anything convenient.

<details>
<summary><b>What that actually involved</b></summary>

- Modular monolith architecture on self-hosted Supabase
- Four vendor integrations: Bunny.net Stream for video, Click and Payme for payments, Eskiz for SMS, with contracts negotiated directly
- Researched and documented the data localization requirements for non-technical stakeholders before any infrastructure was set up

</details>

### [Joytop](https://joy-top.uz) · restaurant discovery for Tashkent *(team project)*
`React Native` `Next.js` `TypeScript` `PostgreSQL/PostGIS`

An app that recommends restaurants based on where you are, who you're with, and what you're in the mood for, across a catalog of 2,000+ venues. My side is the ranking layer, the mobile app, and the database.

<details>
<summary><b>What I own</b></summary>

- **The discovery ranking layer:** PostGIS functions doing occasion-based mood ranking, a per-mood search radius with proximity weighting, and a demographic affinity prior. Replaced a flat price-sorted list.
- **A 9.5s → 400ms search fix:** an `EXISTS` probe was misleading the query planner into sequentially scanning 140K menu rows. The counterintuitive part: empty result sets were the *slow* case, because `EXISTS` has no first match to stop at.
- **Onboarding and auth:** taste capture, phone OTP and email sign-in, location priming, plus the backing profile schema
- 12 database migrations, and full localization across Uzbek, Russian, and English, including Cyrillic/Latin code-switching
- An independent technical review of the AI integration architecture: RAG versus fine-tuning, grounding constraints, and cost ceilings against projected query volume

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

**Frontend Developer Intern @ Mohirlar** (summers 2023 and 2024)
Built the production landing page for [uzbekvoice.ai](https://uzbekvoice.ai) in React and TypeScript. Learned TypeScript from zero in under a month to meet the team's standards, then stayed on the primary client project.

**Mark-It Day 2025**
Organized a school fundraising event in Jeddah that raised over SAR 600,000 (about USD 160,000). Managed vendors, the budget, volunteer teams, and a multi-month timeline.

---

<div align="center">

[LinkedIn](https://www.linkedin.com/in/yusuf-nusrat/) · [yn6281@rit.edu](mailto:yn6281@rit.edu)

<sub>Happy to walk through architecture decisions or share code on request.</sub>

</div>
