---
name: domus-explore-functional-risks
description: Realiza exploración funcional independiente basada en riesgos para descubrir fallos no cubiertos por casos de prueba conocidos. Usar para casos límite, estados inesperados, recuperación, concurrencia, permisos o integraciones.
---

# Explore Functional Risks

Genera charters breves a partir del catálogo de riesgos, arquitectura y cambios reales.

Explora donde aplique: límites y formatos, interrupciones, reintentos, duplicados, navegación atrás, estados vacíos, permisos, concurrencia, degradación de dependencias, persistencia parcial y recuperación. Mantén el alcance proporcional al riesgo.

No hagas fuzzing destructivo ni ataques sobre producción sin autorización específica. Distingue anomalía observada de causa inferida. Cada finding debe contener pasos mínimos reproducibles, resultado esperado/observado, impacto, alcance, evidencia y certeza.

Devuelve `ExploratoryRiskReport`, charters ejecutados, findings, áreas no cubiertas y riesgos residuales.

