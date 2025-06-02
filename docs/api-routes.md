# 🛠️ Dream-Dollars API Routes (v0.1 Draft)

## 🌐 API Endpoints

### 🔑 Auth

- `POST /api/auth/signup`
  - Create new Dreamer account (email/password)
- `POST /api/auth/login`
  - Login Dreamer (email/password or OAuth)
- `POST /api/auth/logout`
  - Logout Dreamer


### 👤 Dreamers

- `GET /api/dreamers/:id`
  - Get Dreamer profile
- `PATCH /api/dreamers/:id`
  - Update profile (pseudonym, avatar, bio)
- `GET /api/dreamers`
  - List all public Dreamer profiles (optional public view)


### 🎬 Projects

- `POST /api/projects`
  - Create new project (title, description, category, etc.)
- `GET /api/projects/:id`
  - Get project details
- `PATCH /api/projects/:id`
  - Update project settings (status, description, etc.)
- `DELETE /api/projects/:id`
  - Delete project (admin-only)
- `GET /api/projects`
  - List all projects


### 🔨 Contributions

- `POST /api/contributions`
  - Log new contribution (hours, task, deliverable)
- `GET /api/contributions/:id`
  - Get contribution details
- `PATCH /api/contributions/:id`
  - Update contribution status (approve/reject)
- `GET /api/contributions`
  - List all contributions


### 📜 Contracts

- `POST /api/contracts`
  - Create contract (Dreamer, IP Assignment, etc.)
- `GET /api/contracts/:id`
  - Get contract details
- `PATCH /api/contracts/:id`
  - Update contract (add Dreamers, update terms)
- `GET /api/contracts`
  - List all contracts


### 💸 Payouts

- `POST /api/payouts`
  - Trigger payout for a project (admin-only)
- `GET /api/payouts/:id`
  - Get payout details
- `GET /api/payouts`
  - List all payouts


### 🔍 Governance

- `POST /api/reports`
  - File ethics/dispute report
- `GET /api/reports/:id`
  - Get report details
- `GET /api/reports`
  - List all reports


## 🛡️ Authentication & Roles

- Dreamers (default)
- Creators (project owners)
- Collaborators (optional access)
- Admins (platform-level access)

**Own your sh*t. Build the dream.**
