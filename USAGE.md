# Cómo usar DOMUS Assurance

## Instalación

Copiar cada carpeta de `skills/` al directorio de skills del runtime que ejecuta DOMUS. Mantener las siete juntas: el orquestador depende de los contratos producidos por las seis skills especializadas.

## Invocación recomendada

Invocar `$domus-assurance-orchestrate` cuando exista una implementación candidata verificable. Proporcionar, como mínimo:

- revisión exacta del código o binario;
- PRD/historias y criterios disponibles;
- especificación y decisiones relevantes;
- superficie y entorno seguro donde ejecutar;
- permisos y acciones prohibidas;
- perfil de riesgo esperado.

Ejemplo:

```text
Usa $domus-assurance-orchestrate para validar la revisión 8f31c2a del flujo
"recuperar contraseña". Usa los artefactos congelados de .domus/baseline,
ejecuta contra staging, no envíes mensajes reales y exige aprobación antes
de alterar datos persistentes. Devuelve verdict, cobertura, hallazgos,
evidencias, riesgos residuales y correcciones mínimas.
```

## Desde DOMUS Core

1. Congelar artefactos y calcular digests.
2. Emitir `AssuranceRequest` al adaptador.
3. Mostrar el plan y pedir únicamente aprobaciones necesarias.
4. Consumir `AssuranceVerdict` sin reinterpretar su evidencia.
5. Si hay `FAIL`, abrir un delta de corrección; después iniciar un run nuevo.

## Uso especializado

- `$domus-derive-acceptance-contract`: preparar criterios antes de implementar o reparar ambigüedades.
- `$domus-simulate-user-journeys`: validar recorridos conocidos en una superficie ejecutable.
- `$domus-explore-functional-risks`: exploración basada en riesgos y casos límite.
- `$domus-verify-cross-layer-contracts`: revisar coherencia UI/API/dominio/datos/eventos.
- `$domus-audit-assurance-evidence`: auditar un paquete de evidencia existente.
- `$domus-decide-release-readiness`: calcular el veredicto sin volver a ejecutar pruebas.

Las skills especializadas pueden invocarse solas para diagnósticos. Solo el orquestador debe emitir el paquete integral de assurance.

