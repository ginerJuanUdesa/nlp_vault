---
tags:
  - nlp
  - model-training
  - efficient-fine-tuning
color: "#4D7BCC"
---

# Adapters

Módulos entrenables pequeños insertados dentro de modelos pre-entrenados para adaptarlos a una tarea específica sin modificar todos los pesos.

## Motivación

El fine-tuning completo tiene varias limitaciones:
- Mover todos los pesos de un modelo grande requiere mucho cómputo y memoria
- Puede llevar al catastrophic forgetting

## Concepto

- Los pesos base del modelo permanecen congelados
- Se agregan nuevos pesos adicionales pequeños
- Solo se entrenan los nuevos parámetros

## Ventajas

- Menos recursos computacionales y de memoria
- Preserva el conocimiento del modelo pre-entrenado
- Permite aprendizaje multi-tarea con un solo modelo

## Tipos

- **Serial adapters:** Insertados en serie entre capas
- **Parallel adapters:** Insertados en paralelo a las capas originales

---

## Relación con otros conceptos

Técnica de fine-tuning eficiente para [[LLMs en general]]. [[LoRA]] es una variante específica. Alternativa al [[Fine-Tuning]] completo. Complementa a [[Transfer Learning]].
