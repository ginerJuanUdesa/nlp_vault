---
tags:
  - nlp
  - fundamentals
  - tokenization
color: "#27AE60"
---

# Tokenización

Proceso de convertir texto en unidades discretas que el modelo puede procesar.

## Funcionamiento

Proceso de segmentar el texto en unidades mínimas (tokens) para que los modelos trabajen con secuencias de tokens. Como los modelos no operan directamente sobre texto raw, este paso es fundamental.

Ese proceso define las unidades mínimas de trabajo del modelo, los tokens, que terminan influyendo en:

- **Calidad de Entrenamiento:** Afecta embeddings, clasificación, traducción, generación, etc. Un buen esquema de tokenización captura unidades con significado lingüístico.
- **Eficiencia:** Menos tokens = secuencias más cortas = menos cómputo por ejemplo.
- **Cobertura de Vocabulario:** El balance entre tamaño de vocabulario y capacidad de manejar palabras no vistas (OOV).

### Niveles de tokenización

- **Caracteres:** Cada carácter es un token (vocabulario muy pequeño, secuencias largas)
- **Palabras:** Cada palabra es un token (no maneja bien palabras nuevas)
- **Subpalabras:** Compromiso entre caracteres y palabras

### Algoritmos

#### BPE - Byte Pair Encoding

Comienza con un vocabulario de caracteres y va fusionando los pares más frecuentes hasta alcanzar el tamaño deseado.

#### WordPiece

Similar a BPE pero con un criterio de selección basado en la probabilidad del modelo.

#### Unigram

Comienza con un vocabulario grande y lo reduce iterativamente manteniendo los tokens que mejor minimizan la pérdida.

## Desafíos

- **Palabras no vistas (OOV):** Palabras que no están en el vocabulario
- **Longitud de secuencia:** Más tokens = más cómputo
- **Idiomas con escritura diferente:** Algunos idiomas no usan espacios

---

## Relación con otros conceptos

Primer paso en el pipeline de procesamiento de [[LLMs en general]], [[Transformers]], [[BERT]], [[GPT]]. Afecta a [[Modelos de Lenguaje]].
