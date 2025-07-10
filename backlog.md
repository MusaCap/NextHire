# 📌 Product Backlog: Resume-to-Job Auto-Application Platform

---

## Epic 1: Resume Upload & Parsing

### User Story 1.1 – Upload Resume
**As a** job seeker  
**I want** to upload my resume in PDF/DOCX/LinkedIn format  
**So that** the system can parse and extract my professional data.

- ✅ Acceptance Criteria:
  - Supports PDF, DOCX, and LinkedIn import.
  - Error handling for unsupported formats.
  - Store original file and parsed JSON.

---

### User Story 1.2 – Parse Resume Data
**As a** system  
**I want** to extract skills, education, experience, and contact info  
**So that** it can be matched to jobs accurately.

- ✅ Acceptance Criteria:
  - Use NLP model for skills and role extraction.
  - Identify and normalize experience durations and job titles.
  - Detect gaps or inconsistencies.

---

## Epic 2: Job Discovery & Matching

### User Story 2.1 – Job Feed Generation
**As a** job seeker  
**I want** to see a curated list of jobs  
**So that** I can easily browse relevant opportunities.

- ✅ Acceptance Criteria:
  - Pull jobs from APIs (LinkedIn, Greenhouse, Lever, etc.)
  - Filter by user preferences (location, remote, salary).
  - Group by relevance and freshness.

---

### User Story 2.2 – Semantic Job Matching
**As a** system  
**I want** to score each job against the user’s resume  
**So that** high-fit jobs can be prioritized.

- ✅ Acceptance Criteria:
  - Use semantic similarity for title/skills.
  - Tag reasons for high or low match.
  - Present match % and recommendations.

---

### User Story 2.3 – Notify of New Matches
**As a** job seeker  
**I want** to receive alerts for high-fit job postings  
**So that** I can apply quickly.

- ✅ Acceptance Criteria:
  - Configurable alert frequency (daily/weekly).
  - Email or in-app notifications.
  - Link directly to matched job card.

---

## Epic 3: Application Automation

### User Story 3.1 – Auto-Fill Application Forms
**As a** job seeker  
**I want** the system to auto-fill job application fields  
**So that** I don’t have to re-enter the same information.

- ✅ Acceptance Criteria:
  - Extract form fields using DOM parsing or API.
  - Map resume data into fields (e.g. work history, education).
  - Preview step before submission.

---

### User Story 3.2 – Auto-Submit Application
**As a** job seeker  
**I want** to optionally auto-submit jobs  
**So that** I can apply with one click or on a schedule.

- ✅ Acceptance Criteria:
  - Toggle for manual review vs auto-submit.
  - Logs each submission attempt.
  - Handle failure gracefully and notify user.

---

### User Story 3.3 – Generate Custom Cover Letters
**As a** job seeker  
**I want** an AI-generated cover letter tailored to the job  
**So that** my applications stand out.

- ✅ Acceptance Criteria:
  - Auto-fill template with resume + job description context.
  - Support user-edited versions.
  - Save templates for future reuse.

---

## Epic 4: Application Tracking

### User Story 4.1 – View My Applications
**As a** job seeker  
**I want** to see a dashboard of all submitted jobs  
**So that** I can track my progress.

- ✅ Acceptance Criteria:
  - Status: Applied, Interviewing, Offer, Rejected.
  - Sorting by date and company.
  - Resume and cover letter used for each.

---

### User Story 4.2 – Track Interview Stages
**As a** job seeker  
**I want** to update or receive updates about interviews  
**So that** I can manage my job pipeline.

- ✅ Acceptance Criteria:
  - Manual or API-based status updates.
  - Calendar integration (Google/Outlook).
  - Add notes per job.

---

## Epic 5: User Preferences & Settings

### User Story 5.1 – Set Job Preferences
**As a** job seeker  
**I want** to define my target roles, locations, and salary  
**So that** I get relevant matches.

- ✅ Acceptance Criteria:
  - Multi-select titles, industries, and locations.
  - Save and edit preferences.
  - Use preferences in matching and alert logic.

---

### User Story 5.2 – Control Privacy & Data Usage
**As a** user  
**I want** to control how my data is stored and used  
**So that** I feel secure using the platform.

- ✅ Acceptance Criteria:
  - Option to delete resume or account.
  - Review access logs for submitted applications.
  - GDPR-compliant consent settings.

---

## Epic 6: Admin & Analytics

### User Story 6.1 – Platform Metrics
**As an** admin  
**I want** to monitor system usage and success rates  
**So that** I can improve performance and reliability.

- ✅ Acceptance Criteria:
  - Metrics: match rate, submit success %, conversion rates.
  - Filter by cohort (location, industry).
  - Exportable reports.

---

### User Story 6.2 – Job Source Management
**As an** admin  
**I want** to monitor or add job source APIs  
**So that** we ensure data freshness and coverage.

- ✅ Acceptance Criteria:
  - Toggle sources on/off.
  - View API health and job volume per source.
  - Retry failed job pulls.

---

## Epic 7: Future Features (Backlog Grooming)

- **Voice Assistant for Job Search**
- **AI Chat Advisor for Resume Rewrites**
- **SMS Interview Reminders**
- **Chrome Extension to Capture Jobs**

---

## Tags & Priorities

| Tag         | Meaning                            |
|-------------|-------------------------------------|
| 🟢 MVP       | Core functionality for first launch |
| 🟡 V1        | Key additions post-MVP              |
| 🔵 Nice-to-Have | Enhancements or future scope       |
