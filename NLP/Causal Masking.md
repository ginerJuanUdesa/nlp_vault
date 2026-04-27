---
tags:
  - nlp
  - model-architectures
  - transformers
  - decoder
color: "#2980B9"
---

# Causal Masking

Mecanismo que impide que los tokens vean información del futuro durante el entrenamiento de modelos decoder.

## Funcionamiento


### Concepto

En modelos generativos como [[GPT]], cada token solo puede atender a los tokens anteriores (y a sí mismo), pero no a los tokens futuros.

### Implementación

Se aplica una matriz triangular inferior a los scores de atención:
- Las posiciones anteriores tienen atención normal
- Las posiciones futuras se ponen a -infinito antes del softmax
- Después del softmax, las posiciones futuras tienen probabilidad cero

### ¿Por qué es necesario?

- Evita que el modelo "haga trampa" viendo la respuesta durante el entrenamiento
- Mantiene la coherencia entre entrenamiento e inferencia
- Esencial para generación autoregresiva

---

## Relación con otros conceptos

Clave en [[GPT]], [[LLaMA]], y [[LLMs en general]] decoder. Complementa a [[Self-Attention]] para generación autoregresiva. Diferencia fundamental con [[BERT]] (bidireccional).
