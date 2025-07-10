# 🧭 Sprint Plan: Resume-to-Job Auto-Application Platform (Windsurf)

---

## 🚦 Sprint 0: Project Initialization & Infra Setup

**Duration:** 1 week  
**Goal:** Lay the foundation for collaboration, repo, and agent workspace in Windsurf.

### 🔨 Tasks
- Set up GitHub repo with CI/CD via Vercel or Railway
- Create shared schema for data model in Prisma/TypeORM
- Configure Windsurf agents:
  - `Agent-Parser`: Resume parsing & enrichment
  - `Agent-Matcher`: Job matching & scoring
  - `Agent-Submitter`: Auto-fill & auto-submit tasks
  - `Agent-Coordinator`: Task and sprint orchestration
- Install core libraries:
  - Frontend: React + Tailwind + Zustand
  - Backend: FastAPI or Next.js API routes
  - DB: PostgreSQL via Supabase

### ✅ Deliverables
- Repo initialized
- Agents scaffolded in Windsurf
- Data model seeded
- Frontend + backend connected

---

## 🚀 Sprint 1: Resume Upload + Job Feed MVP

**Duration:** 2 weeks  
**Goal:** Enable resume upload, parsing, and job feed display.

### 🎯 User Stories
- US 1.1: Upload Resume
- US 1.2: Parse Resume
- US 2.1: Job Feed Generation

### 🧠 Agent Work
- `Agent-Parser`
  - Parse uploaded resume via spaCy + regex
  - Save to `Resume` schema
- `Agent-Matcher`
  - Ingest sample job posts (seeded from JSON)
  - Match titles/skills to job metadata
- `Agent-Coordinator`
  - Sync resume → feed refresh

### 🔨 Dev Tasks
- File upload UI + API endpoint
- Resume parsing backend service
- Job list UI grid (title, company, match score)
- Matching logic (basic keyword + skill match)

### ✅ Deliverables
- User uploads resume
- See job cards with match % and title

---

## 🔁 Sprint 2: Matching Logic + Application Automation

**Duration:** 2 weeks  
**Goal:** Automate matching and allow auto-fill of application forms.

### 🎯 User Stories
- US 2.2: Semantic Job Matching
- US 3.1: Auto-Fill Application Forms
- US 3.2: Auto-Submit Application

### 🧠 Agent Work
- `Agent-Matcher`
  - Upgrade to BERT embeddings + vector store
  - Use Pinecone or pgvector for similarity search
- `Agent-Submitter`
  - DOM extraction using Playwright
  - Auto-fill fields using resume map

### 🔨 Dev Tasks
- Form mapping UI
- Matching explanation UI (skills matched, gaps)
- Job detail page
- Auto-submit toggle

### ✅ Deliverables
- Jobs matched semantically
- Auto-fill form populated with resume fields
- Preview and (optional) auto-submit

---

## 📊 Sprint 3: Tracker, Cover Letter AI, Preferences

**Duration:** 2 weeks  
**Goal:** Allow users to track applications and auto-generate cover letters.

### 🎯 User Stories
- US 3.3: Cover Letter Generation
- US 4.1: View My Applications
- US 4.2: Track Interview Stages
- US 5.1: Set Job Preferences

### 🧠 Agent Work
- `Agent-Submitter`
  - Track each submission
- `Agent-Coordinator`
  - Schedule retries on failed submissions
- `Agent-Parser`
  - Prompt GPT to generate cover letters per role

### 🔨 Dev Tasks
- Cover letter generation UI
- Application pipeline dashboard (Trello-style)
- Settings: title, location, remote, salary
- Calendar API hook for interview stages

### ✅ Deliverables
- Submit + track jobs in dashboard
- Generate role-specific cover letters
- Set and store job preferences

---

## 🧹 Sprint 4: Polish, Testing, Launch Prep

**Duration:** 1 week  
**Goal:** QA, bug fixes, doc gen, and deploy to production.

### 🔨 Dev Tasks
- Unit & integration tests (Pytest / React Testing Library)
- User onboarding flow
- Agent monitoring & observability
- 1-click deploy script

### ✅ Deliverables
- End-to-end tested system
- Deployed MVP
- Demo script & pitch-ready product

---

## 🧠 Agent Roles in Windsurf

| Agent Name        | Responsibilities                                |
|-------------------|--------------------------------------------------|
| `Agent-Parser`    | Resume parsing, NLP, skill extraction            |
| `Agent-Matcher`   | Job ingestion, semantic matching, scoring        |
| `Agent-Submitter` | Form extraction, auto-fill, submission tracking  |
| `Agent-Coordinator` | Workflow orchestration, retries, sync tasks   |
| `Agent-UXBot`     | Generate UI scaffolds, user stories to JSX       |

---

## 🏁 Final Notes

- **Total Duration:** ~6–7 weeks
- **Delivery Mode:** Each sprint concludes with a reviewable PR or demo
- **Collaboration:** Use Windsurf’s UI modeling + agents + async orchestration

