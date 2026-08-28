---
name: domus-assurance-orchestrate
description: Orquesta una revisión funcional independiente de cualquier implementación candidata, más allá de ejecutar tests, y produce un veredicto de liberación trazable. Usar cuando se pida QA asistido por agentes, validación integral, release gate o revisión postimplementación, con o sin DOMUS AI.
---

# DOMUS Assurance Orchestrator

Ejecuta assurance como proceso separado del agente implementador. DOMUS AI es opcional. Acepta requisitos, tickets, PRD, contratos o documentación equivalentes. No modifiques la implementación durante el mismo run.

## Flujo

1. Fija revisión candidata, entorno, artefactos con digest, superficies, permisos y política de riesgo. Si no hay un oráculo verificable o entorno accesible, devuelve `NEEDS_INPUT`.
2. Crea `run_id`, contexto aislado y ledger. No heredes razonamiento privado ni memoria episódica del implementador.
3. Usa `$domus-derive-acceptance-contract` para obtener criterios, journeys, invariantes, riesgos y unknowns.
4. Construye un plan proporcional al riesgo. Coordina `$domus-simulate-user-journeys`, `$domus-explore-functional-risks` y `$domus-verify-cross-layer-contracts` cuando sus superficies apliquen.
5. Detén acciones no autorizadas y solicita aprobación antes de efectos destructivos, costosos o sobre producción.
6. Usa `$domus-audit-assurance-evidence`; no promociones resultados incompletos a hechos.
7. Usa `$domus-decide-release-readiness` con la política fijada.
8. Devuelve `AssuranceVerdict`, cobertura, findings, evidence index, riesgos residuales, unknowns y aprobaciones pendientes.

## Reglas

- Tests existentes son evidencia, no el único oráculo.
- Separa `observed`, `inferred`, `hypothesized` y `unknown`.
- Un defecto bloqueante o criterio crítico sin comprobar impide `PASS`.
- Toda corrección inicia otra revisión y otro run.
