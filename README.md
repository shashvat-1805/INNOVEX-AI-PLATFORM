# INNOVEX — Full-Stack Mini Project

INNOVEX is an AI-assisted innovation procurement and pilot-management platform. This version upgrades the original browser prototype into a runnable full-stack application.

## Stack
- Frontend: existing responsive HTML/CSS/JavaScript INNOVEX interface
- Backend: Node.js + Express REST API
- Database: SQLite via better-sqlite3
- Authentication: bcrypt password hashing + JWT sessions
- Persistence: shared server-side application state
- Audit: server-side audit log for synchronized changes

## Core flow
Challenge → AI/heuristic matching → Proposal → Evaluation → Pilot → Evidence → Validation → Decision

## Full-stack features
- Account registration and login
- Role-aware users: Organization, Evaluator, Startup, Admin
- Shared database instead of browser-only localStorage
- Persistent challenges and startup records
- Shared cross-user project state
- Server-side authentication
- Password hashing
- JWT authentication
- Audit log API
- Existing matching, proposal analysis, risk, pilot, evidence, ledger, radar, graph and multilingual/voice UI preserved
- Health endpoint for deployment checks

## Run locally
Requirements: Node.js 18+

```bash
npm install
npm start
```

Open: http://localhost:3000

Create an account from the login screen. For a classroom demo, create separate Organization, Evaluator, Startup and Admin accounts and open the app in separate browser profiles/incognito windows to demonstrate the workflow.

## API
- `GET /api/health`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/me`
- `GET /api/state`
- `PUT /api/state`
- `GET /api/audit`

## Project structure
```text
INNOVEX_FullStack/
├── index.html
├── app.js
├── server.js
├── package.json
├── .env.example
├── .gitignore
├── README.md
└── data/              # created automatically; SQLite DB lives here
```

## Important mini-project note
The current AI features in the original prototype are transparent heuristic/demo engines. They are suitable for a mini-project demonstration, but they should not be described as a production ML model unless connected to a real model/API and evaluated with a dataset.

## Production next step
For a production deployment, replace the JSON application-state sync with normalized challenge/proposal/pilot tables and add object storage, email/SMS notifications, stronger authorization policies, rate limiting, HTTPS, secrets management and automated tests.
