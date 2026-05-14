# CLAUDE.md — mcp-memory-service Doramagic Pack

> Use this file when Claude Code is your AI coding host. For other hosts, use `AGENTS.md`.

---

## What This Pack Does For Claude Code

This pack loads safe-use instructions for `doobidoo/mcp-memory-service` into Claude Code. It prevents three common failure modes:

1. **Stale or empty memory retrieval** — the consolidation pipeline has version-gated edge cases that silently return outdated results.
2. **Missing memory boundaries** — agents that read/write persistent state without understanding atomicity or eventual consistency.
3. **Opaque installation failures** — the upstream release series (v10.50–v10.55) contains breaking changes that are hard to trace without a pitfall log.

---

## Runtime Instructions

### On Every Session

1. **Read the current task** and determine if it involves `mcp-memory-service`, memory retrieval, or MCP host configuration.
2. **If yes**, load `04_BOUNDARY_RISK_CARD.md` first — it defines what is blocked by default.
3. **Check the pitfall log** (`03_PITFALL_LOG.md`, top 3 actionable items) before running any install, config, or tool command.
4. **Run the smoke check** (`06_EVALS/smoke_check.md`) conceptually before claiming any upstream capability works.
5. **Ask before any external call** — browser, network (except the upstream GitHub API), filesystem writes, or credential access require explicit user approval.

### Before Running Commands

- Check `00_QUICK_START.md` for the official upstream install path.
- Verify the version you are targeting against `03_PITFALL_LOG.md` release-gated pitfalls.
- If the task involves Milvus, graph inference, or embedding hydration: those are **high-risk** paths — stop and confirm user approval.

### If Blocked

1. State which pitfall or boundary applies (by ID from `03_PITFALL_LOG.md` or `04_BOUNDARY_RISK_CARD.md`).
2. Do not proceed past the block.
3. Record the block in `TEST_LOG.md` with: what you tried, what happened, what the expected behavior should be.
4. Report to the user: the block ID, the recovery step, and whether to escalate.

### After Any Tool Call

- If the tool call succeeded: validate the output against the relevant eval in `06_EVALS/`.
- If the tool call failed: open `03_PITFALL_LOG.md`, match to a recovery step, and apply it before retrying.

---

## Keep Tool Usage Explicit

Claude Code reminders:
- Ask before using browser, network, filesystem, or credentials.
- Run `06_EVALS/smoke_check.md` before claiming the pack works.
- If blocked, write the failure into `TEST_LOG.md` or report it to the user.
- Never claim official endorsement by doobidoo/mcp-memory-service.
- Never claim the upstream tool is installed or working without evidence from a passed eval.
