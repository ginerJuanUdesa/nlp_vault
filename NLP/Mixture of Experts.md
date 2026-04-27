---
tags:
  - nlp
  - model-architectures
  - efficiency
  - transformers
color: "#2980B9"
---

# Mixture of Experts

Arquitectura que divide el modelo en múltiples "expertos" especializados, activando solo un subconjunto en cada paso.

## Funcionamiento


### Concepto

La idea de Mixture of Experts es reemplazar la FFN densa de cada bloque transformer por varias FFN distintas llamadas "expertos". Por eso se dice que es una arquitectura sparse. No todos los parámetros trabajan en cada paso, solo una parte. La ventaja es que podés tener un modelo con muchos más parámetros en total sin que el costo de computar cada token crezca proporcionalmente.

La parte de self-attention sigue siendo compartida y densa, mientras que la parte que cambia es la FFN. Cada token entra al gate, el gate decide a qué expertos enviarlo, y solo esos expertos procesan el token.

- Cada experto es una red neuronal pequeña (FFN independiente)
- Un gate aprende a enrutar cada token a los expertos adecuados
- Solo los expertos seleccionados procesan el token

### Ventajas

- Permite modelos enormes con inference eficiente
- Cada experto se especializa en un tipo de dato
- Escala mejor que modelos densos

### Desafíos

- Balance de carga: algunos expertos pueden recibir más trabajo
- Entrenamiento inestable
- Complejidad de implementación

---

## Relación con otros conceptos

Arquitectura para escalar [[Transformers]] y [[LLMs en general]]. Complementa a [[Scaling Laws]] al permitir modelos grandes con inferencia eficiente.
