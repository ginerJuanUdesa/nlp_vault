---
tags:
  - nlp
  - llm
  - knowledge-transfer
color: "#E67E22"
---

# Destilación

La destilación de LLMs busca transferir parte del conocimiento de un modelo grande a uno más chico para obtener un sistema más liviano, rápido y fácil de desplegar.

## Funcionamiento

![[attachments/image71.png]]

### Proceso
1. El modelo grande ("maestro") genera salidas o datos
2. El modelo pequeño ("estudiante") aprende a imitar esas salidas
3. La imitación puede hacerse directamente sobre las salidas del maestro o sobre datos generados por él

### Versión simple
- El LLM grande genera un conjunto de datos a partir de su conocimiento
- Se pasa al LLM chico pre-entrenado
- Se afina con instrucciones específicas

### Ventajas
- Reduce costos de inferencia
- Mantiene parte del comportamiento del modelo grande
- Permite desplegar en entornos con recursos limitados

---

## Relación con otros conceptos

Técnica de compresión para [[LLMs en general]]. Se relaciona con [[Datos Sintéticos]] ya que el modelo maestro genera datos para entrenar al estudiante. Complementa a [[Fine-Tuning]] al permitir que modelos pequeños adquieran capacidades de modelos grandes.
