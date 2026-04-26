---
tags:
  - nlp
  - model-training
  - alignment
  - adaptation
color: "#8E44AD"
---

# Instruction Tuning

Proceso de fine-tuning donde se entrenan modelos de lenguaje para seguir instrucciones en formato natural.

## Funcionamiento

### Formato

A cada ejemplo le damos la instrucción o pregunta seguida de la respuesta deseada todo como una sola secuencia, pero durante el entrenamiento solo computamos la loss sobre los tokens de la respuesta.

La intuición es que el modelo base ya sabe modelar bien texto general, así que no queremos seguir reforzando la continuación de la instrucción, sino solo aprender a generar la respuesta correcta dado el prompt.

### Dataset

En instruction tuning el problema central pasa a ser cómo construir un dataset. Cada ejemplo tiene la forma instrucción → respuesta, y la diversidad de las instrucciones determina qué tan bien el modelo va a generalizar a tareas nuevas.

### Evaluación

La evaluación muestra que instruction tuning mejora de forma consistente el comportamiento del modelo con respecto al modelo base. SFT ya mejora al modelo base en intentar la instrucción correcta, seguir restricciones, y generar respuestas informativas. Los modelos ajustados rinden mejor tanto en truthfulness como en truthfulness + informativeness, y el efecto es más claro cuanto más diverso y de mayor calidad es el dataset de instruction tuning.

### Características

- El modelo aprende a interpretar y seguir instrucciones en lenguaje natural
- Mejora el zero-shot y few-shot learning
- Permite personalización para tareas específicas
- Se puede hacer con [[Datos Sintéticos]] generados por LLMs grandes

### Ventajas

- Mejora la capacidad del modelo para generalizar a nuevas tareas
- Reduce la necesidad de fine-tuning adicional
- Permite usar el modelo con instrucciones en lenguaje natural

---

## Relación con otros conceptos

Evolución de [[Fine-Tuning]] para [[LLMs en general]]. Usa [[Datos Sintéticos]] para escalar. Precursor de [[RLHF]] y [[DPO]] en el pipeline de alignment. Central en [[LLaMA]].
