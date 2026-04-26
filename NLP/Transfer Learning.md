---
tags:
  - nlp
  - model-training
  - adaptation
color: "#8E44AD"
---

# Transfer Learning

Técnica de entrenar un modelo en una tarea general y luego reutilizarlo en tareas específicas.

## Concepto

![[attachments/image54.png]]
![[attachments/image168.png]]

El aprendizaje transferido permite que un modelo entrenado en una tarea grande y general (preentrenamiento) pueda ser adaptado eficientemente para tareas más específicas.

### Pipeline

1. **Preentrenamiento:** El modelo aprende de un corpus grande y variado
2. **Fine-tuning:** Se ajustan los pesos en un dataset específico de la tarea
3. **Evaluación:** El modelo se evalúa en la tarea objetivo

### Formalización

La idea es poder transferir el conocimiento aprendido de la tarea general (tarea pretexto) a la específica. Formalmente, el modelo preentrenado captura patrones generales del lenguaje, y el fine-tuning adapta esos patrones al dominio y formato específico de la tarea objetivo.

### Ventajas

- **Reducción en el tiempo y recursos de entrenamiento:** Especialmente cuando se tienen datos limitados (pocas etiquetas) para la tarea específica.
- Reduce la necesidad de datos etiquetados
- Mejora el rendimiento en tareas con pocos datos
- Permite reutilizar modelos costosos

### Ejemplos

- [[BERT]] pre-entrenado → fine-tuned para clasificación
- [[GPT]] pre-entrenado → fine-tuned para generación
- [[LLMs en general]] → [[Instruction Tuning]]

---

## Relación con otros conceptos

Puente entre [[Pre Training]] y [[Fine-Tuning]]. Aplicado en [[Transformers]], [[BERT]], [[GPT]], y [[LLMs en general]]. Complementa a [[Adapters]] y [[LoRA]].
