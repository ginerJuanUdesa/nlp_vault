---
tags:
  - nlp
  - fundamentals
  - embeddings
  - word-representation
color: "#27AE60"
---

# Word Embeddings

Representaciones vectoriales continuas de palabras que capturan su significado.

## Concepto

### De discreto a continuo

Antes, las palabras se representaban como vectores one-hot (discretos, de alta dimensión). Los word embeddings representan las palabras como vectores densos de dimensión fija en un espacio continuo.

### Propiedades

- Palabras con significado similar están cerca en el espacio vectorial
- Las relaciones semánticas se pueden expresar como operaciones aritméticas
- La dimensión es fija y mucho menor que el tamaño del vocabulario

## Tipos

- **Estáticos:** [[Word2Vec]], [[GloVe]] — un vector por palabra
- **Contextuales:** [[ELMo]], [[BERT]] — el vector depende del contexto

## Ventajas

- Capturan similitudes semánticas
- Reducen la dimensionalidad
- Permiten generalización a palabras no vistas

---

## Relación con otros conceptos

Base de [[Representation Learning]]. Incluye [[Embeddings Estáticos]] y [[Embeddings Contextuales]]. Fundamentado en [[Semántica Distribucional]] y [[Semántica vectorial]].
