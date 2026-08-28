---
name: domus-decide-release-readiness
description: Aplica una política de riesgo a evidencia auditada y emite un veredicto trazable PASS, PASS_WITH_RISK, FAIL, NEEDS_INPUT o INCONCLUSIVE. Usar al cerrar una revisión DOMUS Assurance, sin ejecutar ni corregir la implementación.
---

# Decide Release Readiness

Recibe contrato de aceptación, findings, riesgos, cobertura y `EvidenceAudit`. Aplica la política fijada al inicio; no cambies umbrales para conseguir aprobación.

- `PASS`: todos los criterios críticos tienen evidencia aceptada, no hay bloqueantes y los umbrales se cumplen.
- `PASS_WITH_RISK`: se cumplen mínimos; riesgos residuales explícitos requieren aceptación autorizada.
- `FAIL`: existe incumplimiento confirmado que viola un criterio, invariante o umbral.
- `NEEDS_INPUT`: falta una decisión, contrato o acceso indispensable.
- `INCONCLUSIVE`: se intentó verificar, pero la evidencia no permite concluir.

Devuelve `AssuranceVerdict` con razones, referencias exactas a evidencia, cobertura, riesgos residuales, unknowns, aprobaciones y correcciones mínimas sugeridas. No modifiques código ni ocultes resultados discordantes.

