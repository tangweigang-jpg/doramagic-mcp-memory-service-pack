# AGENTS.md — mcp-memory-service Doramagic Pack

## Goal

Use this pack to help an AI coding agent work with `doobidoo/mcp-memory-service` safely and verifiably — with explicit boundaries, consolidation checks, retrieval evals, and recovery paths for stale memory.

---

## When To Load This Pack

Load this pack when **any** of the following are true:

| Scenario | Example |
|---|---|
| User asks to install or configure `mcp-memory-service` | `pip install mcp-memory-service` or any MCP host setup |
| User asks to evaluate memory retrieval quality | "Does this memory tool return correct results?" |
| Agent needs to verify consolidation pipeline behavior | "What happens after a Milvus embedding hydration failure?" |
| Agent encounters unexpected memory state | Empty results, stale embeddings, or graph inference gaps |
| User asks about memory boundaries or atomicity | "Is this read-write pair atomic?" |
| A memory operation fails silently | No error but outdated/empty retrieval results |

---

## How To Use (Step by Step)

### Step 1 — Restate the task
Before doing anything, restate what the user is asking for in one sentence and confirm the scope.

### Step 2 — Check what the pack covers
Read the following files **before** running any commands:
- `00_QUICK_START.md` — official upstream install path
- `04_BOUNDARY_RISK_CARD.md` — permissions, hard stops, known risks
- `03_PITFALL_LOG.md` — top 3 pitfalls and recovery paths (first section only)

### Step 3 — Identify required actions
Determine whether the task requires:
- External tools (browser, network, filesystem)
- Credentials or secrets
- Modifications to the host AI configuration

If **yes**, stop and ask for explicit user approval before proceeding. Name the specific boundary from `04_BOUNDARY_RISK_CARD.md`.

### Step 4 — Run the smoke eval
Execute the prompt in `06_EVALS/smoke_check.md` conceptually. The agent must:
- Restate the task and boundaries
- Propose one safe verification step
- Not claim the upstream tool is installed or working

### Step 5 — If verification fails
1. Open `03_PITFALL_LOG.md`
2. Match the failure to the top 3 actionable pitfalls (section 1)
3. If not covered, search the full pitfall index (section 2)
4. Apply the recovery step; if none applies, **stop and report**

---

## Inputs Expected From User

- Target host or coding environment
- Task goal and success criteria
- Safety boundary (what is allowed / not allowed)
- Whether external tools, browser, network, filesystem, or credentials are approved

---

## Allowed Actions

- Read files in this pack
- Ask clarifying questions
- Produce a plan
- Run only user-approved verification commands
- Record failures in `03_PITFALL_LOG.md` format

---

## Disallowed Actions

- Do not claim official endorsement by doobidoo/mcp-memory-service
- Do not access secrets by default
- Do not send messages, publish, purchase, delete, or modify external systems without explicit user approval
- Do not claim the upstream tool works until an acceptance check passes
- Do not skip `04_BOUNDARY_RISK_CARD.md` when external tools are involved

---

## Failure Recovery Table

| Failure | Symptom | Recovery Step | When To Stop |
|---|---|---|---|
| **Install fails** | `pip install` exits non-zero | Open `03_PITFALL_LOG.md` → Pitfall #1 (BaseStorage/Milvus override) | License unclear |
| **Memory returns empty/stale** | Retrieval gives no results or outdated data | Check `03_PITFALL_LOG.md` → Pitfall #2 (consolidation/hydration issues) | No evidence in 1h |
| **Agent skips permission check** | Proceeds without user approval | Stop; rewrite boundary in `04_BOUNDARY_RISK_CARD.md` | Always |
| **Smoke eval fails** | Agent claims upstream works without evidence | Rerun `06_EVALS/smoke_check.md` with explicit boundaries | After 2 failures |
| **Version mismatch** | Install succeeds but runtime errors | Check `03_PITFALL_LOG.md` release-gated pitfalls (#4–#6, #9, #15–#18) for version notes | Version unknown |

---

## Failure Recovery (Narrative)

If verification fails, stop and report:
1. Which eval or check failed
2. Expected result vs. actual result
3. Suspected cause (reference a pitfall ID if possible)
4. Recovery step from `03_PITFALL_LOG.md`
5. Whether to stop or continue

---

## Source / Risk Reminder

This is an independent Doramagic pack. Use `SOURCE_MAP.md` for evidence and upstream source links. This pack is not affiliated with or endorsed by doobidoo/mcp-memory-service unless explicitly stated.
