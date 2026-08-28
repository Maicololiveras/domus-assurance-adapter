---
name: domus-audit-assurance-evidence
description: Audita evidencias de QA para comprobar procedencia, integridad, reproducibilidad, cobertura y trazabilidad antes de un release gate. Usar sobre reportes de journeys, exploración, contratos y tests de cualquier proyecto.
---

# Audit Assurance Evidence

Valida cada evidencia contra revisión, entorno, criterio, ejecución y resultado reclamado.

Rechaza o degrada evidencias sin procedencia, de otra revisión, manipuladas, no direccionables o insuficientes para sostener la conclusión. Detecta criterios sin evidencia, evidencia huérfana, resultados contradictorios y cobertura inflada. Los tests previos se aceptan solo si su revisión y entorno son compatibles.

Devuelve `EvidenceAudit` con elementos `accepted`, `rejected`, `conflicting`, brechas de cobertura, lineage y nivel de confianza. No emitas por sí sola el veredicto de release.
