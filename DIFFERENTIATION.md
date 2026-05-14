# Differentiation — doramagic-mcp-memory-service-pack

## What Upstream Provides

The upstream [doobidoo/mcp-memory-service](https://github.com/doobidoo/mcp-memory-service) provides:
- Official install instructions (`pip install mcp-memory-service`)
- Memory service implementation (vector storage, knowledge graph, retrieval)
- Official docs and release notes (GitHub README, architecture docs)
- Version-gated releases (v10.50–v10.55 series with independent release notes)

---

## Why This Doramagic Pack Is Different

| Capability | Upstream | This Pack |
|---|---|---|
| **Agent-hostable instructions** | No (human-only docs) | Yes — `AGENTS.md` / `CLAUDE.md` load into Claude Code and other hosts |
| **Pitfall log with evidence** | No (scattered across 20+ release notes and issues) | Yes — 20 indexed pitfalls with GitHub issue/release URLs |
| **Top 3 actionable recovery steps** | No | Yes — P-01 through P-03 with verify/recover/stop criteria |
| **Eval suite** | No | Yes — smoke check, boundary check, failure check with pass/fail signals |
| **Boundary risk card** | No | Yes — permissions, hard stops, known risks before external calls |
| **Failure recovery table** | No | Yes — structured table mapping failure → symptom → recovery → stop condition |
| **Upstream evidence sourcing** | Raw GitHub | Source Map with version-pinned evidence links |
| **Multi-host support** | MCP host only | MCP host + Claude Code + generic agent hosts via `AGENTS.md` |
| **When-to-load decision guide** | No | Yes — table of concrete scenarios when this pack applies |

---

## What This Pack Deliberately Does NOT Do

- **Not an official mirror** — this pack is independent and not affiliated with doobidoo
- **Not a replacement for upstream docs** — always link to upstream for install commands and architecture
- **Not a generic starter template** — scoped to memory-pipeline safety and failure recovery
- **Not an awesome list** — no curated resource list; only pack-owned assets
- **Not a demo environment** — no live demo; evals test the agent's use of the pack, not the tool itself

---

## Why a Pack Is Needed

The upstream release history (v10.50–v10.55) exposes version-gated edge cases that are:
1. **Not visible in the quickstart** — you only discover them after a failed consolidation or silent staleness
2. **Scattered across release notes** — requires reading 10+ releases to reconstruct the failure map
3. **Not actionable in agent context** — even if you read the release notes, there is no `AGENTS.md` to hand to your coding agent

This pack packages that knowledge as a portable agent instruction set with evals, so you can hand it to any coding agent and get consistent, verifiable behavior.
