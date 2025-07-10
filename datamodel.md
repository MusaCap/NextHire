# Data Model: Resume-to-Job Auto-Application Platform

## 1. User

Represents an individual using the platform.

```json
User {
  id: UUID,
  email: String,
  password_hash: String,
  full_name: String,
  role: Enum("job_seeker", "coach", "admin"),
  resume_id: UUID,
  preferences: Preferences,
  created_at: Timestamp,
  updated_at: Timestamp
}
2. Resume
Stores parsed resume data, either uploaded or generated via LinkedIn.

json
Copy
Edit
Resume {
  id: UUID,
  user_id: UUID,
  original_file_url: String,
  parsed_data: {
    name: String,
    email: String,
    phone: String,
    location: String,
    summary: String,
    education: [Education],
    work_experience: [Experience],
    skills: [String],
    certifications: [String],
    languages: [String]
  },
  created_at: Timestamp,
  updated_at: Timestamp
}

3. JobPosting
Represents job openings fetched via API or scraping.

json
Copy
Edit
JobPosting {
  id: UUID,
  source: Enum("LinkedIn", "Indeed", "Greenhouse", "Lever", "Workable", "Manual"),
  external_id: String,
  title: String,
  company_name: String,
  location: String,
  employment_type: String,
  description: Text,
  url: String,
  salary_range: String,
  requirements: [String],
  tags: [String],
  scraped_at: Timestamp
}

4. JobMatch
Tracks relevance scores between a user’s resume and a job posting.

json
Copy
Edit
JobMatch {
  id: UUID,
  user_id: UUID,
  resume_id: UUID,
  job_posting_id: UUID,
  match_score: Float (0.0–1.0),
  skill_match: [String],
  experience_gap: [String],
  recommendation_level: Enum("high", "medium", "low"),
  matched_at: Timestamp
}

5. Application
Represents an attempt to apply to a job (manual, assisted, or auto-submitted).

json
Copy
Edit
Application {
  id: UUID,
  user_id: UUID,
  resume_id: UUID,
  job_posting_id: UUID,
  status: Enum("pending", "submitted", "error", "reviewed", "interview", "offer", "rejected"),
  method: Enum("manual", "auto_fill", "auto_submit"),
  cover_letter: String,
  submitted_at: Timestamp,
  tracking_url: String,
  feedback_notes: String
}

6. Preferences
User-specific job matching and alert settings.

json
Copy
Edit
Preferences {
  user_id: UUID,
  job_titles: [String],
  locations: [String],
  remote_only: Boolean,
  salary_expectation: String,
  experience_level: Enum("entry", "mid", "senior", "executive"),
  job_alert_frequency: Enum("daily", "weekly", "never")
}
7. ActivityLog
Tracks user interactions with the system.

json
Copy
Edit
ActivityLog {
  id: UUID,
  user_id: UUID,
  type: Enum("login", "resume_upload", "job_viewed", "application_submitted", "settings_updated"),
  metadata: JSON,
  timestamp: Timestamp
}

8. CoverLetterTemplate (Optional Extension)
AI-generated or user-defined templates for cover letters.

json
Copy
Edit
CoverLetterTemplate {
  id: UUID,
  user_id: UUID,
  title: String,
  content: Text,
  context_tags: [String],
  created_at: Timestamp
}
Relationships Overview
User ↔ Resume: 1-to-1 or 1-to-many (if storing version history).

User ↔ JobMatch: 1-to-many.

JobPosting ↔ JobMatch: many-to-many via JobMatch.

User ↔ Application: 1-to-many.

Resume ↔ Application: 1-to-many.

JobPosting ↔ Application: 1-to-many.
