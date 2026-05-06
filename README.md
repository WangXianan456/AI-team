# Agent System

Single-repo operating system for a solo developer with multiple AI roles.

## Goals

- Turn one-person development into a repeatable multi-agent workflow.
- Keep all prompts, policies, tasks, and memory versioned in Git.
- Enforce quality gates before release.

## Structure

```text
agent-system/
  agents/                 # role definitions
  skills/                 # reusable role skill packs
  workflows/              # orchestration and state machine docs
  policies/               # permission and quality policies
  templates/              # task/ADR/release templates
  tasks/                  # live task cards
  memory/                 # long-term memory and project notes
  decisions/              # ADR records
  logs/                   # execution logs (local by default)
  mcp/                    # MCP integration placeholders
```

## Core Roles

- `orchestrator`: plans, dispatches, and approves stage transitions.
- `pm`: converts goals into executable tasks and acceptance criteria.
- `dev`: implements code changes with minimal diff.
- `qa`: validates behavior, regression, and edge cases.
- `ops`: prepares deployment, rollback, and observability checks.

## Workflow

1. Intake requirement.
2. PM creates task card.
3. Orchestrator validates scope and assigns.
4. Dev implements.
5. QA validates.
6. Ops prepares release checklist.
7. Orchestrator (human) approves merge/release.

See `workflows/delivery_flow.md`.

## Quick Start

1. Copy `templates/task_card.md` to `tasks/TASK-xxx.md`.
2. Fill scope and acceptance criteria.
3. Run one delivery cycle following `workflows/delivery_flow.md`.
4. Record decision in `decisions/ADR-xxx.md` if architecture changed.
5. Commit results and logs.

## GitHub

- This folder can be an independent repository.
- Do not commit secrets. Keep keys in `.env` and local secure stores.
- `logs/` and `memory/` may contain sensitive content; sanitize before push.

