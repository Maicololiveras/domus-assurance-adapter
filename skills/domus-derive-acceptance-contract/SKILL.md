---
name: domus-derive-acceptance-contract
description: Convierte requisitos, historias, especificaciones y decisiones de cualquier proyecto en un contrato de aceptación verificable con oráculos, journeys, invariantes, riesgos y vacíos. Usar antes de implementar o validar una funcionalidad, con o sin DOMUS AI.
---

# Derive Acceptance Contract

Construye el oráculo de validación sin inventar intención.

1. Relaciona cada requisito con su fuente y nivel de certeza.
2. Formula criterios observables en forma Given/When/Then solo cuando ayude a eliminar ambigüedad.
3. Define precondiciones, datos, actor, acción, resultado, invariantes y evidencia esperada.
4. Incluye happy path, rutas alternativas, errores, permisos, accesibilidad relevante y recuperación.
5. Marca contradicciones y elementos no verificables como `unknown`; solicita una decisión cuando cambie el comportamiento esperado.
6. Prioriza por impacto y probabilidad.

Devuelve `AcceptanceContract` con `criteria`, `journeys`, `invariants`, `risk_catalog`, `oracle_sources`, `unknowns` y matriz `requirement_to_criteria`.
