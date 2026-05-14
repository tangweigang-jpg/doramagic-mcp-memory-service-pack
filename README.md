# mcp-memory-service Doramagic Pack

Pack version: `v1.0.0` · Last updated: `2026-05-14`

[![Pack v1.0.0](https://img.shields.io/badge/pack-v1.0.0-blue)](./CHANGELOG.md)
[![License](https://img.shields.io/github/license/tangweigang-jpg/doramagic-mcp-memory-service-pack)](./LICENSE)
[![Issues](https://img.shields.io/github/issues/tangweigang-jpg/doramagic-mcp-memory-service-pack)](https://github.com/tangweigang-jpg/doramagic-mcp-memory-service-pack/issues)

Languages: English | [中文](./README.zh-CN.md)

## The Problem

When an AI coding agent uses `doobidoo/mcp-memory-service`, three things go wrong without warning:

1. **Stale memory silently poisons answers** — the consolidation pipeline has edge cases (Milvus embeddings, transitive graph inference) that produce outdated retrieval results with no error signal.
2. **Memory boundaries are invisible** — agents read/write persistent state without knowing which operations are atomic, transactional, or eventually consistent.
3. **Installation failures are opaque** — the service has version-gated release notes (v10.50–v10.55 series) where a single missed patch note means a broken setup with no clear rollback path.

This pack exists so an agent can evaluate, verify, and recover from those failure modes before they reach production.

## Copy / Run / Verify

1. Copy `AGENTS.md` (or `CLAUDE.md`) into your AI coding host.
2. Run the first prompt in `01_PROMPT_PREVIEW.md`.
3. Verify: `node github_pack_agent/scripts/validate-pack.mjs <pack-dir>`
4. If validation fails, open `03_PITFALL_LOG.md` and match the failure to a recovery step.

Quick links:
[Start](./AGENTS.md) · [Prompt](./01_PROMPT_PREVIEW.md) · [Evals](./06_EVALS/) · [Pitfalls](./03_PITFALL_LOG.md) · [Boundary](./04_BOUNDARY_RISK_CARD.md)

## AGENTS.md for Claude Code and AI Coding Agents

Use `AGENTS.md` for agent hosts that support repository instructions. Use `CLAUDE.md` when Claude Code is the target host.

## Pitfalls and Recovery

Start with `03_PITFALL_LOG.md` when setup, permissions, runtime behavior, or verification fails. Top 3 actionable pitfalls are in Section 1; full indexed list is in Section 2.

## When This Pack Helps

Use this pack when you want an AI agent to safely evaluate `mcp-memory-service` with explicit recovery paths and verified boundaries — not by trusting the upstream quickstart.

## What This Pack Adds vs. Upstream

| Capability | Upstream | This Pack |
|---|---|---|
| Agent-hostable instructions | No | Yes — `AGENTS.md` / `CLAUDE.md` |
| Pitfall log with upstream evidence | No | Yes — 20 indexed pitfalls with GitHub URLs |
| Top 3 actionable recovery steps | No | Yes — P-01 through P-03 with verify/recover/stop criteria |
| Eval suite | No | Yes — smoke, boundary, failure checks |
| Boundary risk card | No | Yes — permissions and hard stops |

This is an independent capability pack for `doobidoo/mcp-memory-service`. It is not affiliated with or endorsed by the upstream project.

If this pack helps your agent work from evidence instead of guesses, star the repo so future updates are easier to find. Open an issue for bugs, usage questions, or new pitfall reports.

## Source Attribution

- Upstream: https://github.com/doobidoo/mcp-memory-service (Apache-2.0)
- Pack by [Doramagic](https://doramagic.ai)
