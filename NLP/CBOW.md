---
tags:
  - nlp
  - embeddings
  - word2vec
  - static
color: "#27AE60"
---

# CBOW

Variante de [[Word2Vec]] que predice la palabra central dados los contextos.

## Funcionamiento

CBOW (Continuous Bag of Words) toma las palabras de contexto alrededor y aprende a predecir la palabra central. La ventana de contexto es un hiperparámetro.

### Arquitectura

- Se promedian los embeddings de las palabras de contexto
- El promedio pasa por una capa de proyección
- El output es un softmax sobre todo el vocabulario para predecir la palabra central

### Intuición

Si "el", "gato", "duerme" aparecen juntos frecuentemente, el modelo aprende que el promedio de sus vectores debe apuntar hacia "gato" (o la palabra central correspondiente).

### Diferencia con Skip-gram

- **CBOW:** Contexto → Palabra central (múltiples inputs, un output)
- **Skip-gram:** Palabra central → Contexto (un input, múltiples outputs)

CBOW es más rápido de entrenar pero [[Skip-gram]] tiende a funcionar mejor con vocabularios grandes y datos pequeños.

### Optimización

Usa [[Negative Sampling]] para evitar ajustar todos los pesos del vocabulario en cada paso.

---

## Relación con otros conceptos

Parte de [[Word2Vec]] y [[Embeddings Estáticos]]. Contraste con [[Skip-gram]]. Basado en [[Semántica Distribucional]].
