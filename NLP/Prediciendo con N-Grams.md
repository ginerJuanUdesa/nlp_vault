---
tags:
  - nlp
  - fundamentals
  - language-models
  - n-grams
color: "#27AE60"
---

# Prediciendo con N-Grams

Cómo se calculan probabilidades y se toman decisiones de predicción usando modelos n-gram.

## Predicción

Con n-grams, para decidir qué palabra sigue después de una secuencia, usamos solo las últimas n-1 palabras. Por ejemplo, en un bigram solo miramos la última palabra.

### Ejemplo

Si tengo que predecir "Voy a darle comida al", después de "al" evaluaríamos `p(gato|al)`, `p(perro|al)`, etc., y elegimos la más probable. Si fuera un trigram, miraríamos las últimas dos.

## Probabilidad Conjunta

Se puede calcular la probabilidad conjunta que varía dependiendo de N:

- **Unigrams:** Cada palabra se asume independiente
- **Bigrams:** Cada palabra depende solo de la anterior
- **Trigrams:** Cada palabra depende de las dos anteriores

## Interpolación

Se pueden combinar varios modelos de N-Grams (variando N) para calcular la condicional como un ensamble. La idea es manejar el problema de datos escasos y mejorar la robustez, permitiendo adaptación ante diferentes tamaños de vocabulario y corpus.

---

## Relación con otros conceptos

Parte de [[N-grams]] y [[Modelos de Lenguaje]]. Se evalúa con [[Perplexity]]. Precursor de [[Modelos de Lenguaje con Redes Neuronales]].
