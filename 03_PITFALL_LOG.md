# Pitfall Log — mcp-memory-service Doramagic Pack

> 20 indexed failure modes for `doobidoo/mcp-memory-service`. Top 3 are immediately actionable. Rest is indexed below.

---

## Section 1: Top 3 Immediately Actionable Pitfalls

### P-01: Milvus BaseStorage Override Gap (Installation Blocker)

- **Severity**: medium | **Blocking**: yes if using Milvus
- **Symptom**: `pip install` succeeds but runtime fails with `BaseStorage` override errors when using the Milvus backend.
- **Evidence**: [chore(milvus): track optional BaseStorage overrides + test coverage gaps](https://github.com/doobidoo/mcp-memory-service/issues/888) — issue still open
- **Verify**: Check upstream issue #888 before targeting the Milvus backend. If open, avoid Milvus or confirm a workaround exists.
- **Recovery**: Stop. Do not install with `--use-milvus` or equivalent flag until the issue is resolved or a version with the fix is confirmed.
- **When to stop**: If the issue is open and no workaround is documented, do not proceed to runtime.

---

### P-02: Milvus Consolidation Embedding Hydration Failure (Silent Data Staleness)

- **Severity**: medium | **Blocking**: no | **Silent**: yes
- **Symptom**: After consolidation, retrieval returns results but embeddings are stale or unhydrated — no error raised, just wrong answers.
- **Evidence**: Multiple releases in v10.51–v10.53 series address consolidation and embedding hydration:
  - [v10.51.1 — Milvus consolidation fix](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.1)
  - [v10.52.0 — Cascading Search Fallback + Embedding Hydration on Bulk Reads](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.52.0)
  - [v10.53.0 — Milvus Consolidation Embedding Hydration + GitPython Security](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.53.0)
- **Verify**: Run a retrieval eval immediately after any consolidation operation. Compare embedding vectors before/after.
- **Recovery**: Force re-hydration by triggering a read on the affected entities. If consistent, pin to a known-good version (e.g., v10.53.1+ if available).
- **When to stop**: If re-hydration fails and the issue is not in a released fix, stop using Milvus backend for critical data.

---

### P-03: Cascading Search Fallback Trap (Sparse Result False Confidence)

- **Severity**: medium | **Blocking**: no | **Silent**: yes
- **Symptom**: Semantic search returns sparse results; cascading fallback kicks in silently and returns keyword-matched results with no signal that semantic matching failed.
- **Evidence**: [feat: cascading search fallback when semantic results are sparse](https://github.com/doobidoo/mcp-memory-service/issues/873) — confirmed by v10.52.0
- **Verify**: Run a known query where semantic should dominate but results differ significantly from keyword baseline. Check result metadata for `fallback` flag.
- **Recovery**: If results look plausible but lack semantic grounding, re-run with semantic-only mode to confirm. Do not trust blended results without checking metadata.
- **When to stop**: If the agent presents fallback results as semantically ranked, that is a false confidence signal — correct the record before proceeding.

---

## Section 2: Full Pitfall Index

| ID | Category | Title | Severity | Blocking | Evidence |
|---|---|---|---|---|---|
| P-01 | Installation | Milvus BaseStorage Override Gap | medium | yes (Milvus) | [Issue #888](https://github.com/doobidoo/mcp-memory-service/issues/888) |
| P-02 | Consolidation | Milvus Embedding Hydration Failure | medium | no | [v10.51.1](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.1), [v10.52.0](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.52.0), [v10.53.0](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.53.0) |
| P-03 | Retrieval | Cascading Search Fallback Trap | medium | no | [Issue #873](https://github.com/doobidoo/mcp-memory-service/issues/873), [v10.52.0](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.52.0) |
| P-04 | Installation | v10.51.0 — Plugin hooks live, dynamic /api/types, audit-log example | medium | no | [v10.51.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.0) |
| P-05 | Installation | v10.51.1 — Milvus consolidation fix | medium | no | [v10.51.1 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.1) |
| P-06 | Installation | v10.51.3 — Versioned memory update flag + transitive graph inference | medium | no | [v10.51.3 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.3) |
| P-07 | Installation | v10.54.0 — AND/OR tag filtering for memory_search | medium | no | [v10.54.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.54.0) |
| P-08 | Installation | v10.55.0 — Entity Extraction, Insight Cards, urllib3 bump | medium | no | [v10.55.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.55.0) |
| P-09 | Maintenance | v10.55.1 — Entity Link Storage Fix | medium | no | [v10.55.1 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.55.1) |
| P-10 | Configuration | May modify host AI configuration | medium | no | [host targets](https://github.com/doobidoo/mcp-memory-service) — mcp_host, claude |
| P-11 | Capability | Assumptions not verified against real install | medium | no | [repo README](https://github.com/doobidoo/mcp-memory-service) |
| P-12 | Maintenance | Maintenance活跃度未知 | medium | no | last_activity_observed missing |
| P-13 | Security | No sandbox install executed yet | medium | no | no_demo flag |
| P-14 | Security | Security注意事项 present | medium | no | safety_notes present |
| P-15 | Security | Scoring risks present | medium | no | no_demo; severity=medium |
| P-16 | Security | v10.50.0 — Plugin Hook Scaffolding | medium | no | [v10.50.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.50.0) |
| P-17 | Security | v10.51.2 — OAuth CORS fixes + Milvus embedding hydration | medium | no | [v10.51.2 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.2) |
| P-18 | Security | v10.52.0 — Cascading Search Fallback + Embedding Hydration | medium | no | [v10.52.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.52.0) |
| P-19 | Security | v10.53.0 — Milvus Consolidation + GitPython Security | medium | no | [v10.53.0 release](https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.53.0) |
| P-20 | Maintenance | issue/PR 响应质量 unknown | low | no | issue_or_pr_quality=unknown |

---

## Doramagic Source Extract (Reference)

Project: doobidoo/mcp-memory-service

20 potential pitfalls found, 0 high/blocking. Top priority: Installation — Milvus BaseStorage override evidence.
