---
name: task-completion-audit
description: Audits task completion by comparing task brief, agent output template, and actual repo or build state. Use when closing TASKs, after Cursor execution, or when handoffs look inconsistent.
---

# Task completion audit

## Objetivo

Detectar **desalineación** entre lo pedido, lo declarado y lo existente **antes** de marcar Done.

## Checklist

- [ ] **TASK ID** coherente en brief y `templates/agent_output.md`.
- [ ] **Entregables** del brief: cada ítem tiene archivo/ruta o artefacto citado.
- [ ] **Restricciones** del brief respetadas (sin git ops, sin archivos no relacionados, etc.).
- [ ] **Criterios de aceptación** cubiertos o **explícitamente** recortados con acuerdo (nota en output).
- [ ] **Scope**: no hay features no solicitadas sin nuevo brief.
- [ ] **Handoff** en output: siguientes pasos claros o “ninguno”.

## Salida

| Ítem | Estado OK / Issue | Detalle |
|------|-------------------|---------|

**Veredicto:** **Listo para Done** | **Done con deuda** | **No cerrar** — con razón.

## Si hay Issue

- Severidad y dueño sugerido (Cursor / subagente / Camilo).
- No reemplaza juicio de Camilo en aceptación final.
