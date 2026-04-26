---
tags:
  - nlp
  - model-training
  - adaptation
color: "#8E44AD"
---

# Fine-Tuning

Proceso de ajustar los pesos de un modelo pre-entrenado en un dataset específico de la tarea.

## Funcionamiento

### Proceso

1. Se toma un modelo pre-entrenado
2. Se le da un dataset específico de la tarea con labels
3. Se continúa el entrenamiento con una tasa de aprendizaje baja
4. El modelo se especializa en la tarea objetivo

### Tipos

- **Full fine-tuning:** Se ajustan todos los parámetros
- **Parameter-efficient fine-tuning:** Se ajustan solo algunos parámetros ([[LoRA]], [[Adapters]])
- **Instruction tuning:** Fine-tuning con pares instrucción-respuesta

### Ventajas

- Mejora significativamente el rendimiento en la tarea específica
- Requiere menos datos que entrenar desde cero
- Permite reutilizar conocimiento general del modelo

### Limitaciones

- Puede causar catastrophic forgetting
- Requiere recursos computacionales para full fine-tuning

---

## Relación con otros conceptos

Segundo paso después de [[Pre Training]] en el pipeline de [[Transfer Learning]]. Evoluciona hacia [[Instruction Tuning]]. Se optimiza con [[LoRA]] y [[Adapters]]. Central en [[LLMs en general]] y [[LLaMA]].
