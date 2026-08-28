# Integraciones

El framework depende de puertos, no de proveedores.

## Runtimes

- **Codex:** instala las carpetas en su directorio de skills e invoca `$domus-assurance-orchestrate`.
- **Claude Code/OpenCode:** registra cada `SKILL.md` como agente o comando especializado si no existe compatibilidad nativa.
- **Agente propio:** implementa `ArtifactSnapshotPort`, `SurfaceDriverPort`, `EvidenceStorePort`, `PolicyPort` y `VerdictEgressPort`.

No mezcles el historial del agente que implementó con el contexto del revisor.

## Drivers

| Superficie | Capacidades esperadas |
| --- | --- |
| Web | navegación, accesibilidad, red, capturas y consola |
| API | requests, autenticación, schemas, correlación y estado |
| Desktop | ventanas, accesibilidad, input, procesos y archivos |
| Mobile | gestures, accesibilidad, ciclo de vida y red |
| CLI/TUI | stdin, stdout, stderr, exit codes y archivos |

Cada driver declara lo observable y controlable. Una afirmación que exceda esas capacidades produce `INCONCLUSIVE`.

## Evidencia mínima

```yaml
evidence_id: ev-001
run_id: run-2026-001
candidate_revision: 8f31c2a
criterion_id: AC-03
kind: screenshot|request|response|log|database-state|event|video|test-result
captured_at: 2026-08-28T12:00:00Z
environment: staging
uri: evidence/ev-001.png
digest: sha256:...
producer: domus-simulate-user-journeys
```

## Pipeline

| Verdict | Acción |
| --- | --- |
| `PASS` | continuar |
| `PASS_WITH_RISK` | aprobación autorizada |
| `FAIL` | bloquear |
| `NEEDS_INPUT` | bloquear y pedir decisión |
| `INCONCLUSIVE` | bloquear o revisión manual según política |

