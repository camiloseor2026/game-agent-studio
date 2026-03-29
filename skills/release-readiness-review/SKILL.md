---
name: release-readiness-review
description: Operational release readiness checklist for game slices: build, smoke, comms, telemetry hooks, rollback, and owner sign-offs. Use before external playtests or any milestone labeled as a release candidate.
---

# Release readiness review

## Objetivo

Respuesta **sí / no / no con deuda explícita** a “¿podemos soltar este build?” desde **operación**, no solo gameplay.

## Checklist

| Área | Pregunta | Owner sugerido | OK / Gap |
|------|----------|----------------|----------|
| Build | ¿Binario/PIE reproducible desde instrucciones escritas? | Cursor / Camilo | |
| QA | ¿Smoke mínimo pasado o gaps documentados? | QA | |
| Contenido | ¿Mapa y assets críticos incluidos sin referencias rotas? | World / Art | |
| Comms | ¿Patch notes listas (jugador + interno si aplica)? | LiveOps | |
| Telemetría | ¿Eventos críticos definidos o N/A justificado? | LiveOps | |
| Privacidad | ¿Sin PII nueva no aprobada? | Camilo | |
| Rollback | ¿Plan si el build falla en campo (build previo identificado)? | Cursor / Camilo | |
| Soporte | ¿Canal para feedback / bugs (template QA)? | QA | |

## Veredicto

- **GO** | **GO con deuda** (listar) | **NO-GO** (bloqueadores).

## Reglas

- No sustituye **aceptación de Camilo**; alimenta la decisión.
- Scope charter: no exigir CDN, anti-cheat, etc. si no están en fase.
