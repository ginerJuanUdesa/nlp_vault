---
tags:
  - nlp
  - data
  - synthetic
color: "#7F8C8D"
---

# Datos Sintéticos

Datos generados artificialmente, usualmente usando un LLM grande, para reducir costos de entrenamiento.

## Proceso


1. Se le dan muchas instrucciones o prompts a un LLM grande
2. El modelo genera respuestas candidatas
3. Se seleccionan las respuestas de alta calidad
4. El dataset sintético se usa para entrenar un modelo más pequeño

### Hallazgo clave

Un modelo más pequeño, entrenado con respuestas de alta calidad generadas por el modelo grande, rinde sorprendentemente bien siguiendo instrucciones.

## Ventajas

- Reducen costos de etiquetado
- Escalables: se pueden generar grandes volúmenes rápidamente
- Útiles cuando los datos reales son escasos
- Permiten cubrir diversidad de formatos y tareas

---

## Relación con otros conceptos

Técnica usada en [[Instruction Tuning]] y [[Fine-Tuning]]. Se relaciona con [[Destilación]] al transferir conocimiento de modelo grande a chico. Complementa a [[LLMs en general]] al permitir escalar datasets de entrenamiento.
