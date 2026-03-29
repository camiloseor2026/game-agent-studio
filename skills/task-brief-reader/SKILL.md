---
name: task-brief-reader
description: Parses task briefs faithfully: extracts objective, in-scope, out-of-scope, constraints, and acceptance criteria without adding new requirements. Use at the start of any agent task or when restating what Cursor may implement.
---

# Task brief reader

## Objetivo

Anclar el trabajo al **brief real** (`templates/task_brief.md` o copia con TASK ID), sin **inventar alcance**.

## Pasos

1. Identificar **TASK ID**, **autor**, **ejecutor previsto**, **restricciones** (git, carpetas, archivos no relacionados).
2. Listar **Incluye** y **Fuera de alcance** tal cual; si faltan, marcar **GAP** y escalar a Camilo/Orquestador — no rellenar por iniciativa propia.
3. Copiar **criterios de aceptación** numerados para usarlos en `acceptance-check`.
4. Extraer **referencias** (rutas, docs) como única fuente de contexto extra permitida.
5. Resumen en 3–5 bullets: qué sí hacer / qué no hacer.

## Anti-patrones

- “También podríamos…” que no está en el brief.
- Mezclar otra tarea o feature no citada.
- Ignorar **restricciones** explícitas del brief.
