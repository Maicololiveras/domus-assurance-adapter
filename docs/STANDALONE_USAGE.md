# Uso sin DOMUS AI

DOMUS Assurance es un protocolo de revisión y un conjunto de skills. DOMUS AI puede producir sus artefactos, pero no es una dependencia.

## Requisitos mínimos

1. Runtime capaz de cargar `SKILL.md` o recibir sus instrucciones.
2. Acceso de lectura al código y fuentes funcionales.
3. Revisión candidata identificable.
4. Entorno autorizado.
5. Un driver: navegador, API, terminal, escritorio o móvil.

Sin driver aún se pueden derivar criterios, revisar contratos y auditar evidencia previa, pero no se debe afirmar que se ejecutaron journeys.

## Modos

- **Skills nativas:** instala todas las carpetas e invoca `$domus-assurance-orchestrate`.
- **Agente único:** registra cada worker como agente/comando y entrégalo cuando el orquestador lo requiera.
- **CI/CD:** crea `AssuranceRequest`, ejecuta en un entorno efímero y conserva verdict y evidence pack.

## Proceso

1. **Congela la revisión:** SHA, digest o versión exacta.
2. **Declara fuentes:** requisitos aceptados, contratos, ADR, comportamiento aprobado y tests. Las inferencias siempre se marcan.
3. **Fija autorización:** entorno, acciones permitidas/prohibidas, datos, presupuesto y aprobaciones.
4. **Deriva Acceptance Contract:** fuente, actor, precondición, acción, resultado, evidencia, criticidad y certeza.
5. **Ejecuta por riesgo:** primero críticos; combina journeys, exploración y revisión cross-layer.
6. **Audita evidencia:** revisión, entorno, instante, entrada, salida y criterio relacionado.
7. **Emite verdict:** aplica la política inicial. Una corrección exige un run nuevo.

## Salida sugerida

```text
.assurance/runs/<run-id>/
├── request.yaml
├── acceptance-contract.yaml
├── plan.yaml
├── executions/
├── findings/
├── evidence/
├── evidence-audit.yaml
└── verdict.yaml
```

## Ejemplo WPF

```text
Usa $domus-assurance-orchestrate para validar el build 1.4.0 de una app WPF.
La historia exige crear un proyecto, conservarlo tras reiniciar y mostrar
errores sin perder datos. Ejecuta en QA; no accedas a Oracle PROD. Puedes
usar registros con prefijo QA-ASSURANCE-. Verifica happy path, límites,
reinicio, pérdida de conexión y recuperación.
```

## Ejemplo API

```text
Valida el commit a82d11f en local usando user-story.md y openapi.yaml.
Verifica autorización, idempotencia, errores, persistencia y eventos.
No llames integraciones externas; usa stubs. Conserva requests, responses,
logs correlacionados y estado persistido como evidencia.
```

