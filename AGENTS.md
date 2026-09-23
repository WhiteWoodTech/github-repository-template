# AGENTS.md

Guide for AI coding agents working on this repository.

This file follows the [AGENTS.md](https://agents.md) open standard: it is the single source of truth for every
agent (Codex, Cursor, GitHub Copilot, Jules, Zed, Aider, Claude Code, Gemini CLI...). Keep agent-specific files
as thin pointers to it — never duplicate content in them.

## Agent Compatibility

| Agent | How it loads this file |
|-------|------------------------|
| Codex, Cursor, GitHub Copilot, Jules, Zed, opencode... | Native `AGENTS.md` support |
| Aider | `read: AGENTS.md` in [`.aider.conf.yml`](.aider.conf.yml) |
| Claude Code | [`CLAUDE.md`](CLAUDE.md) imports it with `@AGENTS.md` |
| Gemini CLI | Set `"context": { "fileName": ["AGENTS.md"] }` in `.gemini/settings.json` if needed |

Nested `AGENTS.md` files may be added in subdirectories; the closest one to the edited file takes precedence.

### Project Skills

Project-specific skills follow the [Agent Skills](https://agentskills.io) standard and live in
`.agents/skills/<skill-name>/SKILL.md`, read natively by Codex, Cursor, Gemini CLI and GitHub Copilot.
Claude Code only reads `.claude/skills/`: expose them with a relative symlink `.claude/skills -> ../.agents/skills`.
Create these directories only when the first skill is added.

## Essential Rules

1. **Always consult** this file and the relevant `docs/` file before any modification
2. **Update** documentation when making changes
3. **Follow** conventions established in each `docs/` file

## Documentation Index

| File | Purpose | Description |
|------|---------|-------------|
| [`AGENTS.md`](./AGENTS.md) | AI Guide | This file - conventions and rules for AI agents |
| [`PROJECT_STRUCTURE.md`](docs/PROJECT_STRUCTURE.md) | Architecture | Directory and file organization |
| [`CONVENTIONS.md`](docs/CONVENTIONS.md) | Code style | Naming conventions, code style, git |
| [`TECHNICAL_GUIDE.md`](docs/TECHNICAL_GUIDE.md) | Implementation | API, CI/CD, performance, security, tests |
| [`DESIGN_SYSTEM.md`](docs/DESIGN_SYSTEM.md) | UI/UX | Colors, typography, spacing, accessibility |
| [`COMPONENT_REFERENCE.md`](docs/COMPONENT_REFERENCE.md) | Components | Technical reference for UI components |
| [`FEATURES.md`](docs/FEATURES.md) | Features | Epics, user stories, feature status |
| [`SCREEN_FLOW.md`](docs/SCREEN_FLOW.md) | Navigation | Screen flows and user journeys |
| [`TASKS.md`](docs/TASKS.md) | Tasks | Task tracking and backlog |

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Package Manager | Bun |
| Node Version | ^22.14.0 \|\| >= 24.10.0 |
| Git Hooks | Husky + lint-staged |
| Commit Convention | Gitmoji |
| Commit Validation | commitlint |
| Linting | markdownlint, yamllint |
| Dependency Updates | Renovate (shared preset, automerge) |
| CI/CD | GitHub Actions |

### Available Commands

```bash
bun install           # Install dependencies
bun run lint          # Lint markdown and yaml
bun run lint:md       # Lint markdown only
bun run lint:md:fix   # Auto-fix markdown
bun run lint:yaml     # Lint yaml files
bun run lint:commit   # Validate last commit message
bun run commit        # Interactive gitmoji commit
bun run setup:github  # Apply .github/settings.yml to GitHub
bun run clean:branches # Delete local branches whose PR was merged
```

---

## File Summaries

### PROJECT_STRUCTURE.md

Project structure with source/tests/docs organization. Key points:

- Root files: package.json, AGENTS.md, README.md
- `.github/`: workflows, issue templates, PR template
- `docs/`: all documentation files
- `node_modules/`: dependencies (managed by Bun)

### CONVENTIONS.md

Development conventions. Key points:

- **Naming**: files kebab-case, classes PascalCase, functions camelCase, constants UPPER_SNAKE_CASE
- **CSS**: BEM (block__element--modifier), CSS variables
- **Git branches**: feature/fix/refactor/docs
- **Commits**: Gitmoji convention (emoji + description)

### TECHNICAL_GUIDE.md

Technical implementation guide. Key points:

- **CI/CD**: GitHub Actions workflows (lint on push/PR)
- **Pre-commit**: Husky runs lint-staged automatically
- **Dependency management**: Renovate (weekly, automerge non-major when CI passes)

### DESIGN_SYSTEM.md

UI/UX design system. Key points:

- **Colors**: primary, secondary, semantic (success/warning/error/info)
- **Typography**: system fonts, size scale
- **Spacing**: consistent scale
- **Accessibility**: WCAG 2.1 AA target

### COMPONENT_REFERENCE.md

Component documentation. Key points:

- **Structure**: components organized by type
- **Props**: types and defaults documented
- **Best practices**: composition, accessibility

### FEATURES.md

Feature management. Key points:

- Organization by epics with user stories
- Format: "As a user, I want to [action] so that [benefit]"
- Statuses: Done, In Progress, Planned

### SCREEN_FLOW.md

Navigation and user flows. Key points:

- Flow diagrams between screens
- Entry/Exit points for each screen

### TASKS.md

Project tracking. Key points:

- Current sprint, Backlog, Completed
- Markdown checklist format

---

## AI Agent Specific Rules

### Language Rule

**All written content must be in English**, regardless of the user's prompt language:

- Documentation (markdown files, comments)
- Commit messages
- Tasks and subtasks
- Epics and user stories
- Code comments and JSDoc
- Variable and function names
- Error messages and logs

### Commit Convention

This project accepts **Gitmoji** or **Conventional Commits**:

```bash
bun run commit  # Interactive gitmoji tool
```

**Gitmoji format:** `<emoji> <description>`

| Emoji | Description |
|-------|-------------|
| ✨ | New feature |
| 🐛 | Bug fix |
| 📝 | Documentation |
| ♻️ | Refactor |
| 🔧 | Configuration |

**Conventional format:** `<type>(scope): <description>`

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

Full gitmoji list: [gitmoji.dev](https://gitmoji.dev)

### Fundamental Principles

1. **Read before modifying** - Always read a file before proposing changes
2. **Consult documentation** - Check relevant docs/ files before any task
3. **Respect existing patterns** - Follow the style and conventions already in place
4. **Minimize changes** - Only modify what is necessary
5. **Document changes** - Update docs if behavior changes

### Code Generation Preferences

| Language | Preferences |
|----------|-------------|
| **Markdown** | Follow markdownlint rules, no trailing spaces |
| **YAML** | Follow yamllint rules, consistent indentation |
| **JavaScript** | ES6+, no unnecessary dependencies |
| **TypeScript** | Strict types, explicit interfaces, avoid `any` |

### Pre-commit Checklist

- [ ] Code passes `bun run lint`
- [ ] Documentation updated if necessary
- [ ] Commit uses gitmoji convention
- [ ] No secrets or sensitive data

### Behaviors to Avoid

- Do not create unnecessary files
- Do not add dependencies without justification
- Do not modify project structure without discussion
- Do not ignore linting errors
- Do not comment out dead code, delete it

### Priorities

1. **Functionality** - Code must work correctly
2. **Readability** - Code must be understandable
3. **Consistency** - Follow existing patterns
4. **Simplicity** - Avoid over-engineering

---

*Last updated: 2026-09-24*
