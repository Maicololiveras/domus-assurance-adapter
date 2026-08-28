---
name: domus-verify-cross-layer-contracts
description: Verifica coherencia funcional entre experiencia de usuario, API, dominio, persistencia, eventos e integraciones de una implementación DOMUS AI. Usar cuando una funcionalidad atraviesa dos o más capas o bounded contexts.
---

# Verify Cross-Layer Contracts

Traza cada acción del usuario hasta los contratos técnicos y efectos observables relevantes.

Comprueba nombres y significado, validaciones duplicadas o contradictorias, códigos y mensajes de error, autorización, idempotencia, transacciones, eventos, consistencia esperada y compatibilidad. Usa especificaciones y ADR como fuentes; confirma el comportamiento ejecutable cuando sea posible.

No declares un fallo solo porque la implementación difiere de una preferencia. Reporta desviaciones contra un contrato explícito, una invariante o evidencia observable. Marca drift documental por separado.

Devuelve `CrossLayerContractReport` con trazas, conformidad, drift, findings, evidencia y unknowns.

