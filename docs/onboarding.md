# Developer Onboarding

Welcome to B3dmar. This checklist will get you set up and shipping code within your first day.

## Prerequisites

- [ ] Python 3.13+ installed (we recommend `uv` for environment management)
- [ ] Node.js 22+ and pnpm installed
- [ ] PostgreSQL 16 running locally (or use Docker)
- [ ] GitHub CLI (`gh`) installed and authenticated

## Day 1 Checklist

### Access

- [ ] Accept the GitHub org invite (B3dmar)
- [ ] Get added to the Railway team
- [ ] Get added to the Linear workspace
- [ ] Request `.env.local` credentials from a team lead

### Local Setup

```bash
# Clone the repo
git clone git@github.com:B3dmar/b3dmar.git
cd b3dmar

# Backend
cd backend
uv sync
uv run pre-commit install
uv run alembic upgrade head

# Frontend
cd ../frontend
pnpm install
pnpm dev
```

### Verify Everything Works

- [ ] Backend tests pass: `cd backend && uv run pytest`
- [ ] Frontend dev server starts: `cd frontend && pnpm dev`
- [ ] You can log in at `http://localhost:3000`

## Git Workflow

We use a trunk-based workflow with short-lived feature branches:

```
main <-- staging <-- feat/* | fix/* | chore/*
```

- All changes go through PRs with required CI checks
- Commit messages follow conventional commits: `feat:`, `fix:`, `docs:`, `chore:`
- Keep PRs under 200 lines when possible

## Key Resources

- Architecture overview: [docs/architecture.md](architecture.md)
- API docs (local): `http://localhost:8000/docs`
- Linear project board: ask your team lead for the link
