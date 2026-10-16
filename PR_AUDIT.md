# Existing PR audit — 2026-10-15

## Scope
Audited the two explicitly requested public pull requests before preparing new portfolio changes. No PR was merged, closed, approved, or modified.

## Findings

### `Feliu-persistent-memory#1`
- URL: https://github.com/SantiagoFeliu/Feliu-persistent-memory/pull/1
- State: **OPEN / DRAFT / mergeable**
- Head: `portfolio/case-study-safe-20261015`
- Scope: two documentation files, 118 added lines, no deletions.
- Strengths: clear disclosure boundary; separates the historical FAISS/Ollama implementation from private Cognee/MCP evolution; uses a conceptual Mermaid diagram; explicitly excludes datasets, indexes, credentials, internal paths and topology.
- Review points: the profile README draft is intentionally not the active profile; exact historical measurements and claims remain source-documentation claims and should not be presented as independently revalidated by this audit; the phrase “production deployment” in the source README should remain qualified.
- Decision: **retain as a useful draft; do not merge automatically**. It can be incorporated into the profile work after owner review.

### `cassiopea-local-agent#1`
- URL: https://github.com/SantiagoFeliu/cassiopea-local-agent/pull/1
- State: **OPEN / DRAFT / mergeable**
- Head: `portfolio/engineering-evidence-20261015`
- Scope: one documentation file, 34 added lines, no deletions.
- Strengths: accurately frames the repository as a proof of concept; documents observed endpoints, timeouts, localhost binding and limitations; does not overclaim orchestration or production readiness.
- Review points: README says Qwen2.5-Coder while the PR says Qwen2.5-Coder without pinning the exact tag; the smoke test and local Ollama dependency are not independently executed in this isolated audit; exception disclosure is correctly identified as a future hardening item.
- Decision: **retain as a useful draft; do not merge automatically**. The repository metadata description remains a separate correction.

## Security result
- Public clones of the six priority repositories were inspected at depth 50.
- Working trees were clean at audit time.
- A lightweight pattern scan found no credential-like values; one false positive was the dependency name `tiktoken`.
- This is not proof of absence: gitleaks was not installed in the workspace, and the audit did not inspect private repositories or inaccessible historical objects.

## Portfolio decisions
1. Keep both PRs open and draft pending owner review.
2. Use the PR #1 profile draft as source material, but prepare the final profile README only after validating links and public evidence.
3. Treat `cassiopea-local-agent` as a local FastAPI/Ollama proof of concept, not a production agent platform.
4. Prioritize public evidence from persistent memory, Cassiopea, Felius Transcriber and OpenClaw guide; use the remaining guides as secondary evidence.
