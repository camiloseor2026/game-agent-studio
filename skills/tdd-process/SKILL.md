---
name: tdd-process
description: Defines a test-first workflow for Game Agent Studio: express failing cases and acceptance checks before implementation, then align Cursor briefs and QA validation. Use when planning a feature with the QA agent, splitting TASKs, or reducing silent rework between Gameplay and validation.
---

# TDD process (test-first para este estudio)

## Objetivo

Invertir el orden por defecto: **primero qué debe fallar / qué debe pasar** (casos y criterios observables), **después** la implementación que los satisface. En UE mucho sigue siendo PIE/manual al inicio; la skill **no** exige solo unit tests en C++.

## Ciclo corto

1. **Red (diseño del fallo)** — Listar casos de prueba y criterios de aceptación **antes** de pedir código o blueprints. Cada caso debe ser **observable** (acción + resultado esperado). Si hoy no hay automatización, el “test” es checklist reproducible o script futuro explícito en el brief.
2. **Green (implementación mínima)** — Brief para Cursor/Gameplay con referencia explícita a los casos: “implementar lo mínimo para que pasen T1–T3”.
3. **Refactor (opcional, otro brief)** — Mejorar sin romper casos; correr **regression-review** y acceptance-criteria-validation.

## Entregables del paso “Red” (QA / Orquestador)

- Tabla **ID de caso** | precondiciones | pasos | resultado esperado | prioridad (smoke / full).
- Lista de **criterios de aceptación** copiables al `templates/task_brief.md`.
- Marcar **no automatizable aún** y por qué (editor only, física, etc.).

## Reglas

- Un brief de implementación **no** debería omitir la sección de pruebas si se usó TDD: enlazar IDs de caso o checklist.
- No inflar alcance: casos fuera del slice van a “fuera de alcance” o backlog.
- Tras implementación: **task-completion-audit** + **acceptance-criteria-validation** contra los mismos IDs.

## Unreal (notas prácticas)

- **PIE smoke** cuenta como “test” en fase slice si está documentado.
- **Automation** (Functional Tests, etc.) cuando el proyecto las tenga: un caso automatizado reemplaza o complementa la fila manual en la tabla.
- **Repo** (`tests/`, scripts): mismos IDs de caso en nombres de test o comentarios para trazabilidad.

## Cuándo no forzar TDD estricto

- Spikes de exploración acotados por Camilo (timebox); al cerrar spike, **extraer** casos para el brief real.
- Solo doc/plantillas sin comportamiento ejecutable.
