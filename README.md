# Game Agent Studio

Plataforma experimental de producción game-dev: un **ecosistema de agentes** (orquestador + subagentes) con skills, MCPs, repo estructurado y validaciones, orientado a producir **slices jugables medibles** (no un AAA completo desde el día 1).

## Norte

Demostrar que un pipeline agentic bien diseñado puede reducir tiempo de iteración, exponer cuellos de botella reales, mejorar consistencia técnica y escalar desde un microvertical hacia mayor fidelidad.

## Documentación clave

| Documento | Propósito |
|-----------|-----------|
| [PROJECT_CHARTER.md](./PROJECT_CHARTER.md) | Alcance, principios y límites del proyecto |
| [AGENT_SYSTEM.md](./AGENT_SYSTEM.md) | Roles de agentes, responsabilidades y flujo |
| [SPRINT_01_BACKLOG.md](./SPRINT_01_BACKLOG.md) | Backlog inicial (Semana 1 / Etapa 0) |
| [TECH_DECISIONS_LOG.md](./TECH_DECISIONS_LOG.md) | Registro de decisiones técnicas |

## Estructura del repositorio

```text
/docs          Visión, arquitectura, agentes, roadmap, QA, research, decisiones
/agents        Definiciones y artefactos por agente (p. ej. orquestador en agents/orchestrator/)
/skills        Skills del proyecto (p. ej. project-management, game-dev-lifecycle)
/.cursor       Punto de montaje para Cursor: symlinks a agents/ y skills/ (subagentes + skills)
/mcp           Configuración y notas de MCPs
/prompts       Prompts versionados
/templates     Plantillas (briefs, outputs, bugs)
/tools         Herramientas auxiliares
/scripts       Validaciones y automatización local
/unreal        Proyecto Unreal (añadir aquí el `.uproject` cuando exista)
/tests         Pruebas automatizadas (fuera del engine cuando aplique)
/telemetry     Diseño y hooks de telemetría (conceptual / inicial)
/builds        Artefactos de build (normalmente en .gitignore salvo documentación)
```

## Primer slice (Fase 1)

**Vertical Slice Shooter** pequeño: mapa reducido, loop claro, arma, enemigo/bot, navegación básica, daño/muerte, assets temporales, métricas, QA automatizado + checklist, pipeline documentado.

## Conectar con GitHub

1. Crea un repositorio **vacío** en GitHub (sin README si ya tienes uno aquí).
2. En esta carpeta:

```bash
cd "/Users/camilo.severiche/Documents/Clase Codigo/game-agent-studio"
git remote add origin git@github.com:TU_USUARIO/TU_REPO.git
git branch -M main
git push -u origin main
```

Sustituye la URL por la tuya (SSH recomendado si ya tienes llave en GitHub; si usas HTTPS, GitHub te pedirá token o Git Credential Manager).

## Requisitos locales (cuando toque Unreal)

- Unreal Engine (versión acordada en `TECH_DECISIONS_LOG.md`)
- Toolchain C++ según plataforma de UE

## Licencia

Definir en el charter o aquí cuando corresponda.
