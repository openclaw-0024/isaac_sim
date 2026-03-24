# Agent instructions

This repository is **isaac_sim** (see `README.md`). The tree is currently minimal; extend this file as the project grows.

## Scope and goals

- Prefer small, focused changes that match the stated task.
- Do not add dependencies, credentials, or large binaries unless the task explicitly requires them.

## Repository layout

- `README.md` — project overview.
- `AGENTS.md` — guidance for humans and automated agents (this file).

When new directories appear (e.g. `src/`, `scripts/`, `configs/`), document their purpose here in one line each.

## Conventions (to be refined)

- Match existing naming, formatting, and structure when adding code.
- Keep commits logically scoped with clear messages.

## Build, test, and run

No build or test commands are defined yet. When you add a toolchain (Python, Isaac Sim extensions, Docker, etc.), record the exact commands here, for example:

```bash
# Example placeholders — replace when the project has a real workflow
# pip install -r requirements.txt
# pytest
```

## Safety and secrets

- Never commit API keys, tokens, passwords, or private certificates.
- Do not paste production secrets into issues, PRs, or chat logs used for automation.

## Updating this file

Whenever you introduce a non-obvious workflow, dependency, or architectural decision, add a short note under the right section so future agents and contributors stay aligned.
