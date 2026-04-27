---
tags:
  - nlp
  - model-architectures
  - transformers
color: "#2980B9"
---

# Multi-Head Attention

Mecanismo que permite al modelo atender desde múltiples subespacios de representación en paralelo.

## Funcionamiento


En vez de un solo cálculo de atención, el modelo ejecuta `h` cálculos en paralelo:

### Concepto

En cada layer del Transformer tenemos un bloque de self-attention seguido por una feed-forward. En lugar de hacer una sola atención sobre todo el hidden state, el Transformer reparte la representación total de dimensión d_model en h subespacios más pequeños, cada uno con d_model/h dimensiones.

1. Cada head proyecta Q, K, V en su propio subespacio
2. Cada head calcula su propia atención
3. Las salidas se concatenan
4. Se aplica una proyección lineal final

### ¿Por qué múltiples heads?

Cada head trabaja con una proyección distinta de los embeddings de entrada, por lo que puede enfocarse en relaciones diferentes:

Cada head puede aprender a capturar diferentes tipos de relación:
- Un head puede aprender a capturar dependencias sintácticas
- Otro puede aprender dependencias semánticas
- Otro puede aprender relaciones de co-referencia

---

## Relación con otros conceptos

Componente clave de [[Self-Attention]] en la arquitectura [[Transformers]]. Usado en [[BERT]], [[GPT]], [[LLaMA]], y todos los [[LLMs en general]].
