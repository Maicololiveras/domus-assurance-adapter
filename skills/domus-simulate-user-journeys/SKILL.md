---
name: domus-simulate-user-journeys
description: Ejecuta journeys funcionales como usuarios definidos y captura evidencia reproducible en superficies web, escritorio, móvil, API, CLI o TUI. Usar cuando exista un contrato de aceptación y un entorno autorizado ejecutable.
---

# Simulate User Journeys

Opera exclusivamente dentro de las acciones autorizadas.

1. Selecciona actor, journey, precondiciones y datos desde `AcceptanceContract`.
2. Verifica el estado inicial; no dependas de datos ambiguos o compartidos sin control.
3. Ejecuta pasos observables usando el adaptador de superficie apropiado.
4. Captura entradas, salidas, timestamps, revisión, entorno y evidencia antes/después.
5. Compara con el oráculo. Registra `PASS`, `FAIL`, `BLOCKED` o `INCONCLUSIVE`; nunca completes mentalmente un paso no ejecutado.
6. Restaura datos solo si está autorizado y conserva prueba de limpieza.

Devuelve `JourneyExecutionReport` con resultados por paso, correlación a criterios, evidencias, desviaciones y limitaciones.

