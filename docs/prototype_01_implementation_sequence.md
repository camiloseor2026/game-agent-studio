# Prototype 01 — Secuencia de implementación

**Referencia:** `docs/prototype_01_game_brief.md` (TASK-004) + §1b Design lock-in.  
**Objetivo:** orden de trabajo para Arena-01 en Unreal, sin ampliar alcance.

**Proyecto UE:** `unreal/Arena01/Arena01.uproject` — plantilla **Top Down**, **Blueprint**, Desktop (UE **5.7**). Project Location padre: `…/game-agent-studio/unreal`.

## Resumen del diseño cerrado

- Cámara: **top-down** *o* **fija simple** (documentar cuál en P01-03 + `TECH_DECISIONS_LOG.md`).  
- Jugador: movimiento + **proyectil simple**; **1 hit** mata enemigo.  
- Enemigo: **persigue**; **contacto** = **1 hit** mata jugador.  
- Una arena greybox; reinicio tras muerte; HUD/kills opcional.

---

## Secuencia ordenada

| Orden | ID | Foco | Depende de | Entregable principal |
|------|-----|------|------------|----------------------|
| 1 | TASK-P01-01 | Fundación UE | — | **Hecho:** `unreal/Arena01/Arena01.uproject` + detalle en `TECH_DECISIONS_LOG.md` |
| 2 | TASK-P01-02 | World | P01-01 | Mapa `L_…` una sala; marcadores spawn jugador / enemigo |
| 3 | TASK-P01-03 | Gameplay | P01-02 | Pawn + input movimiento + **cámara** (top-down o fija) |
| 4 | TASK-P01-04 | Gameplay | P01-03 | Proyectil + aplicar daño; **1 hit** elimina enemigo |
| 5 | TASK-P01-05 | Gameplay | P01-04 | Enemigo: perseguir + **overlap/contact** mata jugador (1 hit) |
| 6 | TASK-P01-06 | Gameplay | P01-05 | Reinicio: posiciones/vida tras muerte jugador; respawn enemigo |
| 7 | TASK-P01-07 | Gameplay/UI | P01-06 | HUD mínimo; kills opcional |
| 8 | TASK-P01-08 | QA | P01-07 | `docs/qa/smoke_p01.md` (o equivalente) |
| 9 | TASK-P01-09 | QA | P01-08 | `acceptance-check` vs brief + §1b |

**Regla:** no paralelizar P01-03…P01-07 en la **misma** escena sin brief explícito de integración (Orquestador).

---

## Criterios rápidos por hito

- **P01-04:** Enemigo de prueba puede morir con un disparo (aunque aún no persiga).  
- **P01-05:** El enemigo persigue y el jugador muere al tocarlo una vez.  
- **P01-06:** Tras muerte, repetir ciclo sin salir del mapa.  
- **P01-08:** Lista smoke ≤15 pasos, acción → resultado esperado.

---

## Próximo paso operativo

Copiar `templates/task_brief.md` → **TASK-P01-01** (o el primer pendiente), rellenar con rutas bajo `unreal/` y **Fuera de alcance** copiado del brief §8.
