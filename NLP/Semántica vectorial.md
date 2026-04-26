---
tags:
  - nlp
  - fundamentals
  - embeddings
  - vector-semantics
color: "#27AE60"
---

# Semántica vectorial

Marco conceptual para representar significado en espacios vectoriales.

## Concepto

### Representación continua

El significado de palabras o frases se representa como vectores en un espacio continuo donde:
- Palabras similares están cerca en el espacio
- Operaciones aritméticas capturan relaciones semánticas

### Ejemplos de relaciones

- `vector("Rey") - vector("Hombre") + vector("Mujer") ≈ vector("Reina")`
- `vector("París") - vector("Francia") + vector("España") ≈ vector("Madrid")`

## Aplicaciones

- Similaridad semántica
- Traducción automática
- Búsqueda semántica
- Clustering de documentos

---

## Relación con otros conceptos

Base de [[Word Embeddings]], [[Embeddings Estáticos]], y [[Embeddings Contextuales]]. Derivada de [[Semántica Distribucional]].
