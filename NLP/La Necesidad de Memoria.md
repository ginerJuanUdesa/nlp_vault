---
tags:
  - nlp
  - model-architectures
  - sequence-models
  - memory
color: "#2980B9"
---

# La Necesidad de Memoria

Por qué los modelos de lenguaje necesitan mecanismos para recordar información previa.

## Limitaciones previas

Las limitaciones de los [[N-grams]] es que no pueden generalizar a palabras similares, al estar basados en conteo. La NeuralLM combina embeddings y redes neuronales feed-forward, logrando generalización: si el modelo nunca vio "darle comida al perro" pero sí "darle comida al gato", los embeddings de "perro" y "gato" son parecidos y la probabilidad se transfiere.

### Problema de NeuralLM

Implicaba un input fijo y los parámetros crecen descontroladamente en relación al tamaño del input (contexto).

## ¿Por qué memoria?

La necesidad de memoria surge para procesar eficazmente datos secuenciales:

- **Contexto completo:** Queremos considerar el contexto completo y la relación entre diferentes elementos de la secuencia
- **Información previa es crucial:** En muchas tareas de NLP el contexto anterior (o posterior) de una palabra es crucial para entender su significado
- **Orden es crucial:** Dos oraciones con las mismas palabras pero distinto orden tienen diferente significado. Las redes que pueden "recordar" información previa son capaces de notar estas diferencias

## Solución

Por esta motivación surgen las [[RNNs]], que comparten pesos entre pasos y pueden procesar secuencias de longitud variable.

---

## Relación con otros conceptos

Motivación para [[RNNs]], [[LSTMs]], y eventualmente [[Transformers]]. Puente entre [[N-grams]]/NeuralLM y modelos secuenciales modernos.
