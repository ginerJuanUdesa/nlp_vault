---
tags:
  - nlp
  - fundamentals
  - llm
color: "#27AE60"
---

# Semántica Distribucional

> "Palabras que ocurren en contextos parecidos tienen significados parecidos"


## Principio

El significado de una palabra está determinado por las palabras que aparecen frecuentemente en su entorno. Para una palabra `w`, su contexto se define como las palabras que aparecen a una distancia `k` de `w`.

### Ejemplo

Si "calor" aparece siempre cerca de "sol", "agosto", "playa", y "frío" aparece cerca de "nieve", "invierno", "abrigo", el modelo puede inferir que:
- "calor" y "sol" son similares
- "calor" y "frío" son opuestos

Aun sin conocer "calorim" podemos derivar su significado si aparece en contextos similares a "calor".

## Aplicación

Base teórica para los [[Word Embeddings]]: las representaciones vectoriales aprendidas capturan patrones distribucionales del corpus.

---

## Relación con otros conceptos

Fundamento teórico de [[Word Embeddings]], [[Word2Vec]], y [[GloVe]]. Relacionado con [[Representation Learning]] y [[Semántica vectorial]].
