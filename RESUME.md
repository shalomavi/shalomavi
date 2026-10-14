# Shalom Avichail: Resume and Portfolio Source

> Single source of truth for building the portfolio website. Everything the site needs (bio, experience, skills, projects, copy variants) is in this file.
> Last updated: 2026-10-14. Built from the resume PDF (2026-08-16), the GitHub profile README, and the Fridger repo and promo-video history.

## 1. Identity

- **Name:** Shalom Avichail
- **Title:** Full Stack Software Engineer, specializing in AI-powered applications
- **Location:** Tel Aviv, Israel
- **Languages:** Hebrew, English
- **Email:** shalomavi3@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/shalom-avichail/
- **GitHub:** https://github.com/shalomavi
- **Current portfolio (to be replaced):** https://shalomavi.github.io/
- **Interests:** art, coding, hiking, dancing, exploring new technologies
- **Phone:** deliberately not included, because this repo is public. Add it only if the site needs it.

## 2. Positioning

**One-liner:** Full stack engineer who builds production apps and ships LLM-powered features, with a focus on making the AI part reliable.

**Summary (resume version):**
A Full Stack Software Engineer with hands-on experience building production applications and integrating LLM APIs and AI-driven features. Skilled across the stack, with React and TypeScript on the frontend and Django and PostgreSQL on the backend, and a growing specialization in AI-powered architectures.

**Summary (portfolio version, first person):**
I build full stack applications and the AI features inside them. My day job is React, TypeScript, Django, and PostgreSQL, shipped to web, Android, and iOS. On my own time I build LLM products where the model is treated as an untrusted component: structured output, server-side validation, deterministic fallbacks.

**Themes to emphasize on the site:**
1. Production full stack work (web plus mobile via Capacitor).
2. Reliable LLM integration: validation, fail-closed fallbacks, prompts as a controlled product surface.
3. Building fast with AI tooling (Claude Code, Cursor), including a full app built from a phone.
4. Multilingual and RTL (Hebrew/English) product thinking.

## 3. Experience

### Full Stack Developer, Rokka.ai
**July 2024 to present**
- Contributed to two flagship applications: a CMS for real-time data monitoring and a social-matching app.
- Developed and deployed Android and iOS apps for both products using Capacitor.
- Stack: TypeScript, React, Redux Toolkit, Django, PostgreSQL, GitHub, plus AI-driven analytics for data and customer engagement.
- Containerized services with Docker and Docker Compose, set up Grafana dashboards for monitoring, and used Celery and Redis for asynchronous task processing.
- Worked directly with clients to define and implement tailored solutions; tracked progress and requirements in Jira.
- Integrated LLM APIs to power AI-driven features across applications, enabling intelligent automation and improved user experiences.

### Software Engineer Intern, webeet.io
**January 2024 to July 2024**
- Built full stack features for a smart scheduling app using React, Next.js, TypeScript, Tailwind, Python, and Flask.
- Gained hands-on experience with ML/AI integrations and real-time databases (Firebase, MongoDB).
- Helped build an event-based notification system on WebSocket, supporting real-time in-app and email notifications.

### Founder, Adamot Aley (אדמות עלי)
**May 2020 to December 2022**
- Founded and ran an independent delivery service, managing scheduling, logistics, and customer service end to end.
- Achieved high customer satisfaction through prompt order fulfillment and efficient delivery.

### Financial Analyst, Go No Go
**January 2020 to April 2020**
- Analyzed business plans and ran market surveys, providing data-driven input for strategic decisions.

### Private Tutor
**2019 to 2020**
- Taught economics, statistics, and Excel to undergraduate students.

## 4. Education

- **AI for Developers, Elevation** (February 2026): 30 hours of training in production-ready AI architectures: advanced prompt engineering, RAG pipelines, autonomous agents, and MCP integrations.
- **Software Engineering, Masterschool** (December 2023): immersive one-year program with hundreds of hours of practice and real-world industry projects.
- **B.Sc. Economics, Ben Gurion University** (November 2017).

## 5. Skills

Group these as on the resume. The GitHub profile README lists a longer set; only the resume list is confirmed by professional experience, so mark the rest as "also used" or trim them (see section 9).

**Core (resume):**
- **Languages:** TypeScript, JavaScript, Python, C
- **Frontend:** React, Next.js, Redux Toolkit, Redux-Saga, Tailwind, HTML, CSS
- **Backend:** Django, Django REST Framework, Flask, FastAPI, Node.js, Express.js, Celery, Redis, WebSocket
- **Databases:** PostgreSQL, SQLite, MongoDB
- **Mobile:** Capacitor (Android and iOS)
- **DevOps and tooling:** Docker, Docker Compose, Grafana, Selenium, Git
- **AI-assisted development:** Cursor, Claude Code

**Additional (from GitHub profile README):**
- **Frontend:** Vite, Material UI, styled-components, Sass, i18next (RTL/multilingual), React Hook Form, Zod, Chart.js, Recharts, D3, Mapbox, TanStack Query/Table, Vue, React Router
- **Mobile:** PWA, push notifications
- **Backend:** Django Channels, Supabase (Edge Functions)
- **Data and AI:** Neo4j, pandas, scikit-learn, LangChain/LangGraph, LlamaIndex, Anthropic API, Hugging Face Transformers, web scraping (Selenium, BeautifulSoup)
- **Testing and tooling:** Jest, Vitest, Testing Library, Playwright, pytest, Storybook, ESLint, oxlint, Husky
- **DevOps and cloud:** Jenkins, GitHub Actions, AWS, Google Cloud, Firebase

## 6. Featured project: Fridger

**Live app:** https://fridger-app.netlify.app
**Repo:** https://github.com/shalomavi/fridger
**Promo videos:** in the repo under `docs/promo/` (dark, light, and a combined cut with a dark-to-light wipe, plus a GIF preview)

### Descriptions (pick by space)

**Tagline:**
> Shop together. Let AI plan what to cook.

**Short (one sentence):**
Fridger is a shared shopping list that fills your pantry as you shop, then uses AI (Gemini) to suggest meals from what you actually have.

**Medium:**
Fridger is a shared shopping list that fills your pantry as you shop, then uses AI (Gemini) to suggest meals from what you actually have. Built for households, it works in Hebrew and English and installs as an app on Android.

**Technical:**
Fridger is a React/TypeScript PWA on Supabase for shared shopping lists and pantry tracking. A single Edge Function sends the pantry to Gemini with a JSON response schema, validates the output, reconciles missing ingredients against the pantry, and falls back to static meals on failure. It supports mixed Hebrew/English input.

**Very technical:**
Installable PWA (React, Vite, TypeScript, Tailwind v4) for shared household shopping lists and pantry tracking. Marking an item purchased moves it into the pantry. A single Supabase Edge Function (Deno) then calls Gemini in structured-output mode with a JSON response schema to generate meal suggestions. The server validates the response, reconciles each meal's missing ingredients against the pantry, and falls back to static meals if the call fails or the output doesn't parse. Postgres with RLS handles auth and access control, TanStack Query polls and persists to localStorage for offline reads, and the domain logic is framework-free TypeScript with Vitest coverage. Mixed Hebrew/English input is supported, and language is set per household.

### How it works
1. A household keeps a shared shopping list.
2. Marking an item purchased moves it into the pantry, so there is no separate inventory step.
3. The user asks for meal ideas. One Edge Function sends the pantry to Gemini and gets back 3 meals.
4. The server validates and corrects the result before the client sees it.

### Engineering decisions (portfolio talking points)
- **The LLM is treated as untrusted.**
  - *Structured output:* the call uses `responseMimeType: application/json` with a `responseSchema`.
  - *Validation:* the response is parsed against a schema again on the server.
  - *Fail closed:* if the call fails or the output doesn't parse, the function returns static fallback meals with a `fallback: true` flag.
  - *Reconciliation:* a deterministic pass compares each meal's "missing" ingredients with the real pantry, so the app never tells you to buy something you already own.
- **Prompts as a product surface.**
  - Two modes: *pantry* (anchor on what's on hand, minimize waste) and *any* (browse freely, still report pantry matches).
  - Style types such as fast, healthy, budget, comfort, trending, and dessert are soft nudges phrased as "favor", so several can combine.
  - Diet types such as dairy-only and meat-only (kosher-style separation), vegan, vegetarian, and pregnancy-safe are hard constraints.
  - Every prompt string lives in one file (`prompt.ts`), and the Gemini adapter is swappable.
- **Security boundaries.**
  - The Gemini key exists only in Edge Function secrets; only pantry contents go into the prompt, with no names, emails, or user ids.
  - The Edge Function checks household membership itself; the client never bypasses RLS.
- **Architecture.**
  - `src/domain/` is pure TypeScript with no React or Supabase imports, unit-tested with Vitest.
  - TanStack Query polls (no Supabase Realtime) and persists to localStorage, so the last-fetched data renders offline; writes need a connection.
  - Files are capped at 150 lines and functions at 40, enforced as project rules; no new dependencies without discussion.
- **Multilingual by design.** Language is per household, not per user or browser. Name normalization is lowercase, trim, and collapse whitespace only, because stemming breaks on mixed Hebrew/English input. Details are free text, with no unit conversion and no ingredient taxonomy.

### Stack
React, Vite, TypeScript, Tailwind v4, TanStack Query, Supabase (Postgres, Auth, RLS, Edge Functions on Deno), Gemini API, Vitest, PWA (installable, Android-first), Netlify.

### Built from a phone
Fridger was built with Claude Code, steered from a phone (a proot Linux environment, with no laptop). That constraint shaped the work: no local build or test runs, so changes were verified through the deployed app.

### The promo video, built as code
No ffmpeg or video editor was available on the phone, so the promo video was built as code:
- Motion graphics: a GSAP timeline over HTML and CSS, about 42 seconds at 16:9, with the logo rebuilt from the app's own `favicon.svg`.
- Soundtrack: generated in code with the Web Audio API (music and effects timed to the animation).
- Export: in the browser, using WebCodecs (`VideoEncoder` at 1280x720, 30 fps) and mp4-muxer; sound is rendered offline with `OfflineAudioContext` and encoded with `AudioEncoder`.
- Themes: dark and light versions come from the app's own theme tokens. The final cut switches from dark to light at the midpoint with a quick wipe.
- Side effect: building the video exposed that the favicon, the PWA icons, and the video logo had drifted apart in proportions, and all of them were unified.
- Caveat: the 42-second length comes from the build session; verify against the final export before publishing it as a fact.

## 7. Other projects

Public repos on GitHub, described by their own repo descriptions. Several are course exercises, so frame them accordingly.

| Repo | What it is |
| --- | --- |
| `logs-triage` | Example project: building an AI agent with an agent loop |
| `personal-finance-agent` | Example project: building an AI agent |
| `simple-scheduling-agent` | Example project: a tiny AI agent with an agent loop and terminal IO |
| `rag-lev-boots-project` | Project skeleton to practice RAG |
| `consulting-report-project` | Practice project for context engineering |
| `llm-fundamentals` | Practice project for communicating with LLMs via API |
| `vacation-manager-system` | (no description) |
| `Scraping_comparison` | (no description; web scraping comparison) |
| `multilingual-cv` | A CV that can be translated to multiple languages by choice |
| `recipes_app` and `recipes_app_backend_server` | Web app for handling and displaying recipes: JavaScript, HTML, CSS, FastAPI |
| `moviweb_app` | Movie manager: Flask, HTML, SQL |
| `react-challenge-rick-and-morty` | React challenge |
| `Spent`, `lugo-test`, `user-library`, `User-list` | (no description) |
| `Understand-Anything` | A repo in the account whose description reads like a third-party project; check whether it is a fork before listing it |

**Suggested order for the site:** Fridger first, then the AI-agent and RAG repos as a "learning in public" group, then older web apps in a smaller "earlier work" group.

## 8. Reusable copy

### LinkedIn post (current version)

> **I built a full-stack app with an LLM backend, a PWA, and a motion-graphics promo video, all from my phone.**
>
> It's called Fridger, a shared shopping list for my household. Mark an item as bought and it moves into the pantry. Then Gemini suggests meals from what we actually have.
>
> The model is the least trusted part of the system, so the app checks its work:
>
> → **Structured output.** A JSON response schema, validated again on the server.
> → **Fail closed.** If the call fails or the output doesn't parse, it returns static fallback meals and flags them.
> → **Reconciliation.** If the model says to buy something already in the pantry, the server corrects it.
> → **Hard vs. soft rules.** "Fast" or "budget" are gentle nudges. "Vegan" or "pregnancy-safe" are hard constraints.
>
> The Gemini key lives in one Supabase Edge Function. It checks household membership itself, and the client never bypasses RLS. The core logic is plain TypeScript with no framework imports, and it handles mixed Hebrew/English lists.
>
> **The promo video is code too.** My phone has no ffmpeg or video editor, so I wrote the motion graphics as a GSAP timeline over HTML/CSS. The soundtrack is generated with Web Audio. WebCodecs encodes the MP4 in the browser.
>
> Claude Code did the heavy lifting, and I steered it from my phone.
>
> React · TypeScript · Tailwind · Supabase · PWA
>
> https://fridger-app.netlify.app
>
> #AI #LLM #Supabase #BuildInPublic

A warmer, story-style variant also exists. Its dinner-table framing was a guess at the origin story, so confirm the facts before using it.

### Tagline options
- Shop together. Let AI plan what to cook. (Fridger)
- Full stack engineer building reliable AI-powered products.

## 9. Notes for the portfolio build

**Open items (need the owner's input):**
- Replace the stale line in the GitHub profile README ("working on a therapists search-by-location project") with Fridger.
- Decide which skills to keep. The profile README lists around 100 technologies; the resume lists fewer. Items not backed by the resume or a project here (Neo4j, Vue, Jenkins, scikit-learn, AWS, Google Cloud) should be cut or shown as secondary if they can't be defended in an interview.
- Decide whether to mention being open to work.
- The resume does not yet mention Fridger, Supabase, or Gemini; the next resume revision should add Fridger as a project.
- Confirm the promo video length and the tool-free build claim against the final export.
- Add testimonials, screenshots, or case studies if available; none are collected here.

**Suggested site structure:** Hero (title plus one-liner) → Featured: Fridger (live link, video, engineering decisions) → Experience → Skills → Other projects → Contact (email, LinkedIn, GitHub).

**Tone:** direct and technical, with some warmth. Lead with what was built and the decisions behind it. Avoid listing every technology.

**Assets available:**
- Fridger promo videos and a GIF preview: https://github.com/shalomavi/fridger/tree/main/docs/promo
- The Fridger logo: `public/favicon.svg` in the Fridger repo (fridge icon; the app's main color is teal).
- Resume PDFs in Google Drive (folder "CV"): latest is `Shalom_Avichail_Resume_pdf.pdf` (2026-08-16).

**Sources:**
- Resume PDF (Google Drive, 2026-08-16)
- GitHub profile README (`shalomavi/shalomavi`)
- Fridger repo README, `suggest-meals` Edge Function, and `docs/promo` commit history
- The Claude Code session that built the promo video
