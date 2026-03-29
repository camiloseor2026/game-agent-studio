# Sprint 1 execution plan

**Task:** TASK-001  
**Focus:** Operational setup only — **no** gameplay code, **no** multiplayer, **no** advanced physics, **no** large-scale art production.

## Sprint 1 objective

Make the studio **executable**: GitHub-ready workflow, frozen operational rules, Unreal install/version recorded, UE project shell agreed and documented, orchestration path from brief → Cursor → acceptance — so Sprint 2+ can target the vertical slice without redoing foundations.

## Ordered tasks

| Order | Task ID | Task | Owner (primary) | Depends on |
|-------|---------|------|-----------------|------------|
| 1 | TASK-S01-01 | Confirm `main` + remote GitHub; ensure `docs/branch_policy.md` matches how Camilo will merge | Camilo + Cursor | — |
| 2 | TASK-S01-02 | One-page vision in `docs/vision/game_vision.md` (genre direction, tone, non-goals for phase 1) | Camilo | — |
| 3 | TASK-S01-03 | Install UE + toolchain; record **exact** engine version and target OS in `TECH_DECISIONS_LOG.md` | Camilo | — |
| 4 | TASK-S01-04 | Architecture note: `docs/architecture/repo_and_unreal_layout.md` (where `.uproject` lives, what is gitignored, who generates project files) | Orquestador (contenido) → Cursor (repo) | TASK-S01-01 |
| 5 | TASK-S01-05 | Create Unreal project under `unreal/<ProjectName>/` per layout doc; no gameplay systems beyond default template if needed for open/compile | Cursor | TASK-S01-03, TASK-S01-04 |
| 6 | TASK-S01-06 | Copy `templates/task_brief.md` + `templates/agent_output.md` into `docs/` as **worked examples** (one fictional completed task) or add `templates/README.md` pointing to real TASK-S01-* briefs | Cursor | TASK-S01-01 |
| 7 | TASK-S01-07 | Stubs in `prompts/` for orchestrator + one subagent (short system-style prompts, under one page each) | Orquestador (contenido) → Cursor (repo) | TASK-S01-04 |
| 8 | TASK-S01-08 | `docs/roadmap/post_sprint_01.md`: 5–10 bullets for Sprint 2 (vertical slice) with explicit **not in S2** list | Camilo + Orchestrator | TASK-S01-02, TASK-S01-05 |

*Orchestrator role (asignado por Camilo, p. ej. Camilo u otra persona) mantiene IDs y briefs; Cursor ejecuta solo tareas con rutas explícitas en el brief.*

## Expected deliverables

- Remote repo in sync with local; branch policy followed for any feature work.
- `docs/vision/game_vision.md` exists and matches charter boundaries.
- `TECH_DECISIONS_LOG.md` contains UE version + toolchain decision.
- `docs/architecture/repo_and_unreal_layout.md` exists.
- `unreal/<ProjectName>/` with a project that opens in the logged UE version (empty or template level only).
- At least one filled example brief + output, or `templates/README.md` linking to real S01 briefs.
- Two prompt stubs under `prompts/`.
- `docs/roadmap/post_sprint_01.md` with Sprint 2 scope sketch.

## Acceptance criteria (sprint)

1. A new contributor can read `README.md`, this plan, and `orchestrator_spec.md` and know **who does what** next.
2. No task in this sprint requires multiplayer, advanced physics, or art pipeline beyond placeholders documented as “later.”
3. UE version is **single and written**; no ambiguity in `TECH_DECISIONS_LOG.md`.
4. Every **Cursor** task (4–7) had a **Task ID** and used `templates/task_brief.md` before edits.
5. Camilo signs off **done** on vision + post-Sprint-1 roadmap bullets.

## Out of scope (Sprint 1)

Shooter loop, weapons, AI, greybox art pass, automated gameplay tests, MCP wiring, telemetry implementation, market research deliverables beyond stub prompts.
