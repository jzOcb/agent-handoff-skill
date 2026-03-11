# Agent Handoff Skill (Dual Edition)

Two production-ready handoff skill variants so users can pick the right runtime:

- `handoff-openclaw/` → optimized for OpenClaw workflows (`sessions_spawn`, `message`, topic dispatch)
- `handoff-claude/` → tool-agnostic version for Claude.ai / Claude Code

## Which version should I use?

| Environment | Use |
|---|---|
| OpenClaw (Telegram/topic/sub-agent orchestration) | `handoff-openclaw` |
| Claude.ai / Claude Code (generic handoff docs) | `handoff-claude` |

## What this skill standardizes

Required sections in every handoff doc:
- Task
- Context
- Scope (Do / Don't)
- Acceptance Criteria
- Resources

Optional sections:
- Research Summary
- Plan
- Constraints
- Priority / Deadline
- Notes

## Install

### OpenClaw
Copy the desired skill folder into your skills directory.

### Claude.ai
Zip the desired folder and upload in Claude Skills settings.

## Why this exists

Most handoffs fail because context is incomplete or acceptance criteria are vague.
This skill enforces a compact, executable handoff format so the receiving agent can start immediately.
