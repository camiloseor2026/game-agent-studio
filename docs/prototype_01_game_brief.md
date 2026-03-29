# Prototype 01 — Game brief

**Task ID:** TASK-004  
**Tipo:** micro-prototipo jugable (validación de flujo agentic + Cursor + UE)

---

## 1. Prototype name

**Arena-01** — one-room shooter micro-vertical.

---

## 2. Purpose of the prototype

Validar que el **sistema de trabajo** (brief → Orquestador → subagentes → Cursor → QA) puede producir un **loop jugable mínimo** en Unreal sin inflar alcance. No demuestra ambición de producto final; demuestra **ejecución coordinada y medible**.

---

## 3. Core gameplay loop

1. Aparecer en una **sala única** (arena).  
2. **Moverse** y **disparar** hacia un enemigo.  
3. **Eliminar** al enemigo (un impacto = muerte) **o** ser eliminado por contacto o disparo del enemigo (según lo más simple de implementar en el primer pase).  
4. Si el jugador muere: **reinicio** al estado inicial de la partida (misma sala, enemigo respawn).  
5. (Opcional) Incrementar un **contador de kills** visible en pantalla.

---

## 4. Player actions

- Movimiento en plano (WASD o equivalente; cámara fija o third/first person mínima — **una** opción acordada en implementación).  
- Disparo principal (un tipo de proyectil o hitscan; **uno**).  
- Sin inventario, sin sprint obligatorio, sin habilidades extra.

---

## 5. Enemy behavior

- **Un** tipo de enemigo.  
- Se acerca al jugador a velocidad constante (simple “move toward player”) **o** dispara proyectil lento si es más rápido de probar; elegir **una** variante en el primer TASK de Gameplay.  
- **Un golpe** del jugador lo elimina.  
- Sin oleadas, sin pathfinding complejo: NavMesh opcional; si no, movimiento directo sin obstáculos dinámicos.

---

## 6. Win / lose conditions

| Estado | Condición |
|--------|-----------|
| **Victoria de ronda** (opcional para P01) | Enemigo eliminado → respawn enemigo + sumar kill (si hay contador). |
| **Derrota** | Vida del jugador ≤ 0 (o un hit = muerte si se simplifica aún más). |
| **Reinicio** | Tras derrota (y opcionalmente tras victoria de ronda): recargar posiciones/vida en **la misma** arena sin menú complejo (ej. tecla R o auto-respawn tras 2 s). |

No se exige menú principal ni pantalla de créditos.

---

## 7. Minimum feature scope

- **Un** mapa / nivel: una habitación acotada (greybox UE: BSP o cubos).  
- **Un** personaje jugador con colisión y movimiento.  
- **Un** arma o componente de disparo con daño aplicable al enemigo.  
- **Un** enemigo con salud = 1 “unidad” de daño del jugador.  
- **HUD mínimo**: vida (o indicador binario vivo/muerto) + opcional contador de kills.  
- **Game Mode** o lógica equivalente que gestione reinicio.  
- Contenido **placeholder** (materiales/cubos); sin pipeline de arte final.

---

## 8. Out of scope

- Multiplayer, netcode, servicios en vivo, telemetría implementada.  
- Física avanzada, destrucción, cover system, IA con árboles complejos, más de un tipo de enemigo.  
- Mundo grande, múltiples salas, narrativa, audio final, cinemáticas.  
- Economía, progresión meta, guardado persistente más allá de lo necesario para PIE.  
- Optimización de producción (LOD fino, light bake complejo).

---

## 9. What this prototype validates (agent workflow)

| Área | Qué se prueba |
|------|----------------|
| **Orquestador** | Orden de TASKs (ej. convenciones → proyecto UE → greybox → pawn → daño → enemigo → HUD → reinicio → QA smoke). |
| **Gameplay** | Specs mínimas y conversión a briefs ejecutables para Cursor. |
| **World** | Brief de layout de una sola arena + greybox sin creep. |
| **Art/Rigging** | Placeholders y naming; sin arte final. |
| **QA** | Smoke checklist + `acceptance-check` / criterios del brief; `tdd-process` opcional (casos antes de código en el siguiente ciclo). |
| **Market / LiveOps** | **No** son bloqueantes para P01; pueden correr en paralelo solo como docs si Camilo lo pide. |
| **Transversal** | `task-brief-reader`, `scope-guard`, `repo-safe-editing`, `structured-handoff`, `unreal-task-framing` en cada paso. |

---

## 10. Suggested next implementation tasks (post-brief)

Orden sugerido (ajustar IDs en backlog real):

1. **TASK-P01-01** — Registrar versión UE y confirmar ruta del `.uproject` (`TECH_DECISIONS_LOG.md` + `unreal/`).  
2. **TASK-P01-02** — Greybox arena única (`World` + Cursor): dimensiones mínimas, spawn jugador/enemigo marcados.  
3. **TASK-P01-03** — Pawn jugador: movimiento + cámara (`Gameplay` + Cursor).  
4. **TASK-P01-04** — Disparo + daño 1-hit al enemigo (`Gameplay` + Cursor).  
5. **TASK-P01-05** — Enemigo: un comportamiento simple + muerte (`Gameplay` + Cursor).  
6. **TASK-P01-06** — Vida jugador + muerte + reinicio (`Gameplay` + Cursor).  
7. **TASK-P01-07** — HUD mínimo + kill counter opcional (`Gameplay` o UI mínima + Cursor).  
8. **TASK-P01-08** — Smoke checklist específico P01 (`QA` → `docs/qa/` o output de agente).  
9. **TASK-P01-09** — `acceptance-check` formal contra este brief + ajuste de criterios si hay GAPs documentados.

Cada TASK debe usar `templates/task_brief.md` con **Fuera de alcance** explícito y referencia a este documento.

---

## Acceptance criteria (brief-level)

- [ ] Un jugador puede completar al menos un ciclo: entrar → disparar → matar enemigo → (opcional) ver contador → morir o reiniciar y repetir.  
- [ ] Todo ocurre en **una** arena sin cargar otros niveles.  
- [ ] Ningún ítem de la sección **Out of scope** aparece como requisito en los briefs hijos sin decisión de Camilo.  
- [ ] Existe documento de smoke P01 que referencie este brief.
