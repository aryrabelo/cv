# Ary Ribeiro Rabelo

Senior Ruby on Rails & Full-Stack Engineer · Tech Leadership, Production Ownership & AI Tooling  
Santarém, PA, Brazil · Remote  
Phone: +55 (93) 99122-3444  
Email: [aryrabelo@gmail.com](mailto:aryrabelo@gmail.com)  
Website: [aryrabelo.com](https://aryrabelo.com/en/)  
GitHub: [github.com/aryrabelo](https://github.com/aryrabelo)  
LinkedIn: [linkedin.com/in/aryrabelo](https://www.linkedin.com/in/aryrabelo/)

<!-- Master CV = version F (2026-10-20), rendered from output/cv-master-2026-10-20-F.html. Keep this file and that HTML in sync. -->

## About

Self-taught software engineer with 20+ years of experience, specializing in Ruby on Rails since 2012 and working remotely with US startups since 2019 (Rails, GraphQL, React, TypeScript, PostgreSQL). Experienced across cloud and production infrastructure- AWS (EC2, S3, CloudFront), Cloudflare (end-to-end type-safe TypeScript services and edge infrastructure), Heroku, Docker, Kamal, and CI/CD pipelines (GitHub Actions, CircleCI) - and I own what I ship, from on-call to observability (Sentry, New Relic, PagerDuty).

I have led teams since early in my career: as CTO of Soprojetos and, in 2026, as tech lead of a five-person development team on a six-month applied research project at UFOPA's Embrapii unit, building an AI mobile app. At every company since 2019, I have also written the technical specifications and task breakdowns. Alongside Rails, I build AI features and developer tooling, integrating language models into real products with human-confirmation guardrails and browser-based CI evaluation.

**Open source:** I built **[itaruby](https://github.com/aryrabelo/itaruby)**, a Ruby type checker in Rust that infers types without annotations. It found the issues behind **10 of my merged upstream pull requests** (crash fixes in Discourse and fastlane, dead-code removals in Rails).

## Core Skills

- **Backend & Languages:** Ruby on Rails, Ruby, Sorbet, TypeScript (end-to-end type-safe), JavaScript, SQL, Rust (itaruby), Python
- **Frontend:** React, TypeScript, GraphQL (Apollo, Relay), REST, Hotwire (Turbo, Stimulus), Vue 3
- **Databases & Search:** PostgreSQL, Redis, Elasticsearch, MySQL
- **Cloud, Infrastructure & CI/CD:** AWS (EC2, S3, CloudFront, SQS), Cloudflare (Workers/edge, serverless TypeScript infrastructure), Heroku, Docker, Kamal, DigitalOcean (Dokku), GitHub Actions, CircleCI
- **Architecture & Data Flows:** Rails monoliths with separate services, services over typed APIs, async messaging (AWS SQS in production; Kafka, RabbitMQ in test and personal projects), Sidekiq/Redis queues, idempotent retries
- **Observability & Analytics:** Sentry, New Relic, Honeybadger, PagerDuty, Mixpanel, PostHog
- **Testing & Quality:** RSpec, Capybara, Playwright, Cypress, Jest, MiniTest, TDD/BDD
- **AI & Developer Tooling:** Claude Code and coding agents, LLM product integrations, MCP servers and CLIs

## Work History

### Tech Lead and External Researcher — doaudio R&D project · UFOPA, Embrapii Bioforest Unit
**May 2026 – Dec 2026** · Six-month applied R&D project executed by UFOPA's Embrapii unit (Brazil's industrial R&D network) on doaudio, an AI app that records, transcribes and summarizes Brazilian Portuguese audio, which I built and launched on the App Store and Google Play in March 2026

- **Tech lead of a five-person development team:** defined the architecture, broke down the work, and reviewed every pull request, on independent, end-to-end type-safe TypeScript services on Cloudflare Workers that talk over typed APIs.
- **Designed the live AI pipeline:** AssemblyAI multilingual streaming transcription with speaker diarization feeds a Cloudflare Worker that batches turns to Jev, TypeSafe AI's typed-decision model, which labels each turn (question, action, number, decision or a user category) with a calibrated confidence. Labels below 0.6 go to human review instead of being shown as fact, and a failed batch never invents a label.
- **15 releases shipped with the team** (May–Oct 2026): real-time notes with AI summaries, minutes and tasks; team task lists and shared project folders; RevenueCat subscriptions and paywall; a referral program; a redesigned onboarding; and a browser extension. Tracked the cost of every AI decision per user and rate-limited live classification by plan.
- Admitted by an exceptional rector's authorization as the unit's only external researcher. Technical work complete; the engagement ends with the R&D project in December 2026.

### Senior Full Stack Software Engineer II — Canix
**Mar 2024 – May 2026** · All-in-one seed-to-sale ERP for cannabis cultivators, distributors and manufacturers; multi-tenant Rails, GraphQL, TypeScript and React

*Role eliminated as the engineering team was downsized (the CTO and other engineers also left).*

- **CI from ~30 to ~6 minutes and 30% lower infrastructure costs:** the suite was flaky and the team had stopped trusting it. I led the Cypress to Playwright migration in small reversible PRs and made the tests deterministic (stable selectors, order-independent specs, video recordings on failure).
- **1,942 files migrated from Relay to Apollo Client** after two earlier attempts by previous teams had been reverted: changed every file deterministically with codemods, used AI agents to check each changed file and add test coverage, and shipped behind a feature flag with the tests passing before merge and a rollback ready.
- **Packages screen load from ~12 s to ~2 s** by eliminating N+1 queries with batch loaders, adding targeted indexes, and moving heavy reports to background jobs.
- **Owned the Metrc state-compliance sync**, a high-volume integration on Sidekiq/Redis. When an oversized batch blocked the queue and scheduled syncs overlapped, I isolated the job in its own queue, added retry limits and idempotency, and fixed the root cause.
- Built UAT-Agent, an AI QA step in CI: on every pull request it opens the preview app like a real user, reads the acceptance criteria with Claude Code, validates them, and records a highlight video for PMs and engineers.
- Built compliance integrations (Metrc, Biotrack, LeafLink, QuickBooks Online) with the team and integrated the Rails monolith with separate label and document printing services, in a Sorbet-typed codebase.

### Senior Full Stack Software Engineer — Flowspace
**2020 – Feb 2024** · YC-backed on-demand warehousing and fulfillment for Fortune 500 brands and e-commerce startups; Rails monolith, GraphQL API, React and TypeScript

- Built the **AI Command Center** as a founding contributor, an isolated pack with clear service boundaries: an in-app chat where an LLM searches orders and inventory, adjusts stock, and generates tags, with mandatory user confirmation before any database change.
- **Removed manual data entry for freight documents:** built an inbound email ingestion pipeline that processed Bills of Lading asynchronously, matching orders, parsing documents, and notifying ops on Slack.
- Built the DoorDash same-day delivery integration end to end with the team, from merchant terms of service to warehouse dispatch flows.
- **Support stopped needing engineering for routine issues** after I built ActiveAdmin tools for the most common escalations.
- Took part in the production on-call rotation, introduced ViewComponents to speed up template testing, and mentored new engineers in an async remote team.

### Full Stack Engineer — Cleary
**2019 – 2020** · Employee experience platform founded by two ex-Twitter employees; clients included JUUL, Flexport, and Armory

Rails API with a React and TypeScript frontend on AWS, using SQS in production for asynchronous communication between services, with GitHub and CircleCI CI/CD pipelines.

- **60% faster article creation** without background workers (a strict product requirement).
- Built and maintained HRIS integrations with Workday and Namely.
- Migrated 500+ pages to the Froala editor while preserving previous layouts, and built a reusable React comment architecture.

### Full Stack Developer — Monde Sistemas
**2016 – 2019** · Multi-tenant platform for 1,700+ travel agencies

- **26,000+ MiniTest tests migrated to RSpec in one week.**
- **90% faster selected SQL queries** using full-text search.
- Shipped daily with 100% test coverage (RSpec, Capybara, code review).

### Earlier career
**2003 – 2017**

- **Soprojetos**, CTO and Rails developer (2003 – 2016, modernization 2026): an architecture-plans e-commerce store I started with my parents, built from scratch in PHP and then Ruby on Rails, leading a team of up to 7. Built an automated digital project delivery pipeline on **AWS (S3 + CloudFront)**, Rails, and Redis, plus faceted search with **Elasticsearch**, and **scaled to 1.8M monthly visits (peaks of 3M) and 300+ req/s on a single 2 GB Heroku dyno**. In 2026, spent roughly six weeks modernizing it to current Rails, Hotwire (Turbo & Stimulus), Docker and Kamal container deploys.
- **DescontosHoje**, founder (2017): coupon mobile app in React Native (Expo) backed by a Ruby on Rails API on DigitalOcean with Dokku and CircleCI, built with a friend to learn the stack. Shipped to the App Store and Google Play and reached **5,000+ downloads and 60+ merchant trials in month one**, but did not take off.

## Open Source Contributions

- **30 merged pull requests** to open source repositories since May 2026: 6 crash fixes in Discourse (one in the AI bot retry handler), 3 dead-code removals in Rails plus a fix a Rails maintainer landed with me as co-author, a fastlane fix, Archon, beads, an offline test suite for SerpApi's official MCP server, and 15 in software-factory, where I added Ruby support.
- Built [itaruby](https://github.com/aryrabelo/itaruby), a Ruby type checker in Rust (MIT, alpha) that infers types instead of requiring annotations; I only submitted candidate diagnostics after reproducing each error under MRI with the project's own test suite.
- Built **RepoDocs**, a zero-dependency Python CLI published on PyPI that drives Claude Code, OMP, or Codex CLI to generate a source-cited wiki for any repository: every claim links to an exact file and line, pages build in parallel with SHA-256 incremental rebuilds, and a citation lint checks the output.
- Wrote the **NEXT ACTION protocol**, a drop-in instruction for coding agents (Claude Code, Codex, Cursor, Gemini CLI) that makes every response end in exactly one unambiguous next step: done, a decision for the human, a human-only step, or a wait on something external.
- Published **Tapa**, a Rust and Tauri Markdown editor that coding agents can inspect and edit over MCP, and **serpapi-agent-toolkit** (plus searchapi-agent-toolkit, planqueue, and omp-burnrate), TypeScript CLIs for coding agents; serpapi-agent-toolkit uses **~17x fewer tokens per call** than the official MCP server.

## Education

### Master's in Process Engineering — PPGEP / UFPA
**2016 – 2018** · Thesis: applied artificial neural networks (Python, Keras) to identify sales opportunities in marketing data

## Community & Mentoring

- Help run a community of 150+ IT students in Santarém, mentor early-career programmers, and speak a couple of times a year at regional universities about software engineering, remote work culture, and AI.
