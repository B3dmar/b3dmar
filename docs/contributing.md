# Contributing to B3dmar

Thanks for your interest in contributing. This guide covers the basics.

## Getting Started

1. Fork the repository
2. Clone your fork and set up the dev environment (see [onboarding.md](onboarding.md))
3. Create a feature branch from `main`
4. Make your changes
5. Submit a pull request

## Branch Naming

Use descriptive prefixes:

- `feat/short-description` for new features
- `fix/short-description` for bug fixes
- `docs/short-description` for documentation
- `chore/short-description` for maintenance tasks

## Commit Messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(sync): add retry logic for failed webhook deliveries
fix(api): handle null timezone in user preferences
docs: update onboarding checklist with Linear setup
chore: bump psycopg to 3.2.10
```

Keep the subject line under 50 characters, imperative mood, no trailing period.

## Pull Requests

- Keep PRs focused and under 200 lines when possible
- Include a clear description of what changed and why
- Add tests for new functionality
- Make sure CI passes before requesting review

## Code Style

- **Python**: Formatted with `ruff format`, linted with `ruff check`
- **TypeScript**: Formatted with Prettier, linted with ESLint
- **EditorConfig**: Install the EditorConfig plugin for your editor

## Running Tests

```bash
# Backend
cd backend
uv run pytest

# Frontend
cd frontend
pnpm test
```

## Reporting Issues

Use the issue templates when filing bugs or feature requests. Include enough context for someone unfamiliar with the problem to reproduce it.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
