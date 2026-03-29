# Orchestrator specification

**Task:** TASK-001  
**Audience:** Camilo, Cursor; Orquestador y subagentes como roles de flujo documentado en el repo.

## Role

The Orchestrator is the **single routing layer** between product intent and specialized work. It does not replace Camilo (priorities, acceptance) or **Cursor** as the **local execution path** for file changes. It **turns goals into sequenced work packages** and **tracks handoffs** between subagent responsibilities and Cursor-driven edits.

## Responsibilities

1. Maintain a **clear order of work** (what runs first, what blocks what).
2. **Decompose** charter / roadmap items into tasks that fit one brief each (`templates/task_brief.md`).
3. **Assign** each package to exactly one primary executor: Cursor (files), a named subagent role (plans/docs in `agents/<role>/` or `docs/`), or Camilo (decisions only).
4. **Consolidate** subagent outputs using `templates/agent_output.md` so nothing is “lost in chat.”
5. **Gate scope**: reject or split requests that violate `PROJECT_CHARTER.md` or active sprint boundaries.
6. **Trigger validation** conceptually (checklists, scripts when they exist); record what was run or skipped.

## Inputs

| Input | Source |
|-------|--------|
| Priorities, go/no-go | Camilo |
| Vision, charter, sprint boundaries | `PROJECT_CHARTER.md`, `SPRINT_01_BACKLOG.md`, `docs/sprint_01_execution_plan.md` |
| Agent boundaries | `AGENT_SYSTEM.md` |
| Task detail | Filled `templates/task_brief.md` per task |
| Technical constraints | `TECH_DECISIONS_LOG.md`, `docs/naming_conventions.md`, `docs/branch_policy.md` |

## Outputs

| Output | Where |
|--------|--------|
| Ordered task list + dependencies | Sprint execution plan (updated as needed) or backlog doc |
| One brief per executable task | Copy of `templates/task_brief.md` with **Task ID** set |
| Consolidation after delegation | Short summary + links to `templates/agent_output.md` instances |
| Escalation notes | Brief section “Escalación” or new entry for Camilo / `TECH_DECISIONS_LOG.md` |

## Delegation logic (subagents)

1. **Classify** the goal: gameplay systems, world/layout, art/rigging, QA, market, liveops — per `AGENT_SYSTEM.md`.
2. **One primary subagent** per package. If two domains are required, **split** into two briefs unless the work is purely documentation that touches both (then one brief with two bullet owners).
3. **Cursor** executes only when the brief explicitly lists repo paths, file creation, or automation; otherwise the subagent produces **plans/docs** first, then a follow-up brief for Cursor.
4. **Order**: dependencies first (e.g. naming + branch policy before mass file creation; architecture before UE project layout).
5. **No parallel conflicting edits**: same area of repo → sequential briefs.

## Escalation to Camilo

Escalate **immediately** (stop expanding scope) when:

- Charter conflict (AAA scope creep, multiplayer, monetization, open world, etc.).
- **Irreversible** choice: engine version, repo layout change, legal/licensing, budget/tooling.
- **Stalemate** after one retry: subagent output still fails acceptance criteria.
- **Missing priority**: two valid sequences exist and the brief does not say which wins.

Escalation format: problem in 2–3 sentences, **two options**, recommendation, what is blocked.

## External guidance (only if Camilo requests)

Not part of the internal workflow. Use **neutral** outside input when Camilo explicitly wants a second opinion.

| Situation | Action |
|-----------|--------|
| Unclear how to split a goal | External advisor suggests decomposition; Orchestrator/Camilo turns it into briefs |
| Large architecture / UE + repo layout | Outline in `docs/architecture/`; **Camilo** approves; **Cursor** implements per brief |
| Prompt/skill design | Spec in brief; owner subagent or Orchestrator defines content; **Cursor** commits under `prompts/` or `skills/` |
| Tradeoff (quality vs speed vs risk) | **Camilo decides**; any external input is advisory only |

Routine sequencing inside an agreed sprint plan does **not** require external consultation.

## Scope-control rules

1. **Sprint boundary**: only tasks in the active sprint execution plan (or Camilo-approved addendum).
2. **No gameplay production** unless the sprint doc explicitly moves to that phase; orchestration docs and operational setup stay **tooling, process, and structure**.
3. **No new folders** at repo root without Camilo OK (align with existing tree).
4. **Single source of truth**: if charter and backlog disagree, **charter wins** until Camilo updates one of them.
5. Every outbound package must include **out of scope** in the brief to stop drift.
