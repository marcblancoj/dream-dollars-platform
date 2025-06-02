# 📊 Dream-Dollars DB Schema + Auth Flow (v0.1 Draft)

## 📦 Database Schema (Supabase/Postgres)

### Tables

- `dreamers`
  - `id`: UUID (PK)
  - `email`: String
  - `pseudonym`: String
  - `region`: String
  - `avatar_url`: String (optional)
  - `bio`: Text
  - `auth_provider`: String (email, Google, GitHub)

- `projects`
  - `id`: UUID (PK)
  - `creator_id`: UUID (FK -> dreamers.id)
  - `title`: String
  - `description`: Text
  - `category`: String (film, music, game, etc.)
  - `status`: Enum (draft, active, completed)
  - `created_at`: Timestamp

- `contributions`
  - `id`: UUID (PK)
  - `dreamer_id`: UUID (FK -> dreamers.id)
  - `project_id`: UUID (FK -> projects.id)
  - `role`: String
  - `task`: Text
  - `hours_logged`: Integer
  - `dream_dollars_awarded`: Decimal
  - `status`: Enum (pending, approved, rejected)
  - `signed_contract_url`: String

- `contracts`
  - `id`: UUID (PK)
  - `project_id`: UUID (FK -> projects.id)
  - `type`: Enum (dreamer, IP assignment, TOS, privacy)
  - `signed_by`: UUID[] (FK -> dreamers.id)
  - `file_url`: String
  - `created_at`: Timestamp

- `tasks`
  - `id`: UUID (PK)
  - `project_id`: UUID (FK -> projects.id)
  - `assigned_to`: UUID (FK -> dreamers.id)
  - `description`: Text
  - `due_date`: Date
  - `status`: Enum (open, in progress, complete)
  - `deliverable_url`: String

- `payouts`
  - `id`: UUID (PK)
  - `project_id`: UUID (FK -> projects.id)
  - `amount`: Decimal
  - `date_paid`: Date
  - `stripe_payout_id`: String

- `audit_logs`
  - `id`: UUID (PK)
  - `action`: String
  - `user_id`: UUID
  - `timestamp`: Timestamp


## 🔐 Auth Flow

- Sign Up: Email/Password, Google OAuth, GitHub OAuth
- Onboarding: Select pseudonym, region, avatar (optional)
- Role-based access: Creator, Dreamer, Collaborator
- Email confirmation required
- Magic link login (optional future feature)

## 🚀 Next Steps

- Finalize DB schemas based on feedback
- Create Supabase tables
- Integrate with Next.js frontend
- Set up Stripe Connect for payouts

**Own your sh*t. Build the dream.**
