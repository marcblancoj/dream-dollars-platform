# 📊 Dream-Dollars ER Diagram (v0.1 Draft)

## 🧱 Entities

### 🧑‍🚀 Dreamers
- id (PK)
- email
- pseudonym
- region
- avatar_url
- bio
- auth_provider

### 🎬 Projects
- id (PK)
- creator_id (FK → Dreamers.id)
- title
- description
- category
- status
- created_at

### 🛠️ Contributions
- id (PK)
- dreamer_id (FK → Dreamers.id)
- project_id (FK → Projects.id)
- role
- task
- hours_logged
- dream_dollars_awarded
- status
- signed_contract_url

### 📜 Contracts
- id (PK)
- project_id (FK → Projects.id)
- type
- signed_by (array of Dreamer IDs)
- file_url
- created_at

### 📋 Tasks
- id (PK)
- project_id (FK → Projects.id)
- assigned_to (FK → Dreamers.id)
- description
- due_date
- status
- deliverable_url

### 💸 Payouts
- id (PK)
- project_id (FK → Projects.id)
- amount
- date_paid
- stripe_payout_id

### 🛡️ Audit Logs
- id (PK)
- action
- user_id
- timestamp


## 🔗 Relationships

- Dreamers ↔ Projects (1:N) via creator_id
- Dreamers ↔ Contributions (1:N)
- Projects ↔ Contributions (1:N)
- Projects ↔ Contracts (1:N)
- Projects ↔ Tasks (1:N)
- Dreamers ↔ Tasks (1:N)
- Projects ↔ Payouts (1:N)
- Dreamers ↔ Audit Logs (1:N)


**Own your sh*t. Build the dream.**
