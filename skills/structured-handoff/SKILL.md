---
name: structured-handoff
description: Formats agent outputs for clear handoffs: summary, artifacts, decisions, blockers, and next owner using the studio templates. Use when finishing a subagent turn or passing work to Cursor, Camilo, or another role.
---

# Structured handoff

## Objetivo

Que el siguiente rol **no reinterpreté** el trabajo: misma información, misma estructura.

## Formato base

Alinear con `templates/agent_output.md`:

1. **Resumen** — 3–5 líneas: qué se hizo, resultado, pendientes.
2. **Artefactos** — tabla o lista: tipo → ruta en repo.
3. **Decisiones** — bullets; las que afectan producto/repo → también `TECH_DECISIONS_LOG.md` si aplica.
4. **Riesgos / bloqueos** — severidad + quién desbloquea.
5. **Handoff** — explícito:
   - **Para Cursor:** rutas y acciones concretas (o “ninguno”).
   - **Para Orquestador:** qué re-secuenciar.
   - **Para Camilo:** qué decidir.

## Reglas

- Enlaces **relativos al repo** cuando sea posible (`docs/...`, `skills/...`).
- No mezclar handoff en párrafos largos sin secciones tituladas.
