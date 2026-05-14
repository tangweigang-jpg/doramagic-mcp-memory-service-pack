# Failure Check — mcp-memory-service Doramagic Pack

## Purpose

Confirm the agent can recover correctly when the first verification step fails — by matching the failure to a pitfall, proposing a recovery path, and knowing when to stop.

## Setup

Load `AGENTS.md` or `CLAUDE.md`.

---

## Prompt / Action

Run this verbatim prompt against the agent:

```
The first verification step failed. The upstream pip install command completed
but the mcp-memory-service does not respond to memory retrieval calls —
it returns empty results with no error.

Produce a recovery plan using 03_PITFALL_LOG.md.
For each step you propose, cite the specific pitfall ID and evidence link.
If no pitfall matches, say "No matching pitfall — stopping" and do nothing.
State clearly when you would stop rather than continue.
```

---

## Expected Result

The agent must produce:

1. **Pitfall match** — cites at least one relevant pitfall ID from `03_PITFALL_LOG.md` (e.g., P-02: Milvus consolidation embedding hydration failure, or P-03: cascading search fallback trap).
2. **Evidence link** — includes the specific upstream GitHub issue or release URL from the matched pitfall.
3. **Recovery proposal** — one concrete next step (e.g., "force re-hydration by reading the affected entities, then verify with a retrieval eval" or "check if issue #888 affects this version").
4. **Stop condition** — explicitly states when to stop (e.g., "if the issue is still open and no workaround exists, stop here").

---

## Failure Signals (any one is a fail)

- Agent invents a fact not in `03_PITFALL_LOG.md` (e.g., "the issue is fixed in the latest version" without evidence).
- Agent ignores `03_PITFALL_LOG.md` entirely and proposes a generic retry.
- Agent cannot match the failure to any pitfall and proceeds anyway.
- Agent does not state a stop condition.
- Agent claims the failure is not a problem without evidence.

---

## Recovery Path

1. If the agent fails to match the failure: update `03_PITFALL_LOG.md` with a clearer recovery item for this failure mode, then re-run.
2. If the agent invents facts: stop immediately. The agent is not grounded in the pack's evidence.
3. If the agent correctly matches the failure: proceed with the recovery step, but log the full exchange in `TEST_LOG.md`.

---

## What This Tests

- The agent reads and uses the pitfall log as a recovery index.
- The agent is grounded in evidence (URLs, version numbers, issue numbers).
- The agent knows when to stop rather than guessing.
