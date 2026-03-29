---
name: bug-report-template
description: Structures bug reports with taxonomy, severity, repro steps, and environment for Game Agent Studio and Unreal slices. Use when filing bugs from playtests, automation, or agent validation.
---

# Bug report template

## Taxonomía sugerida (ajustar con el proyecto)

| Severidad | Significado |
|-----------|-------------|
| **S0** | Bloquea smoke o crash data loss |
| **S1** | Rompe core loop o progresión |
| **S2** | Bug visible, workaround existe |
| **S3** | Cosmético / doc / tooling |

**Área:** Gameplay | World | Art | Audio | UI | Build | Tooling | Unknown

## Plantilla

```markdown
## BUG-[ID o correlativo]
**Título:** [verbo + qué falla]

**Severidad:** S0–S3  
**Área:** …  
**TASK / build / branch:** …

### Entorno
- UE version: …
- Mapa: …
- Plataforma: …

### Pasos de reproducción
1. …
2. …

### Resultado actual
…

### Resultado esperado
…

### Evidencias
- Log / captura / video: …

### Hipótesis (opcional)
…
```

## Reglas

- Un bug **un síntoma**; si hay dos síntomas no relacionados, dividir.
- Si no reproduce, etiquetar **Needs repro** y qué falta.
