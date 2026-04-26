---
tags:
  - nlp
  - embeddings
  - word-representation
  - static
color: "#27AE60"
---

# GloVe

**Global Vectors for Word Representation** — modelo de embeddings que usa estadísticas de co-ocurrencia global de todo el corpus.

## Funcionamiento

![[attachments/image158.png]]
![[attachments/image176.png]]
![[attachments/image28.png]]

### Diferencia con Word2Vec

Como fue mencionado, [[Word2Vec]] se basa en pequeñas ventanas de contexto. En cambio, la idea con GloVe es poder aprovechar información global del corpus de manera directa.

### Matriz de frecuencias

La frequency matrix es una tabla que resume cuántas veces distintas palabras aparecen relacionadas en un corpus. En el caso más simple, es una matriz palabra-contexto donde cada celda (i,j) contiene cuántas veces la palabra `j` aparece en el contexto de la palabra `i`.

### Matriz de co-ocurrencia

En vez de solo mirar ventanas locales, GloVe construye una matriz X donde X_ij cuenta cuántas veces la palabra `j` aparece en el contexto de la palabra `i` en todo el corpus.

### Idea central - Hipótesis distribucional

La idea general es que el significado de una palabra puede inferirse a partir de cómo se distribuyen las palabras que aparecen a su alrededor. GloVe toma esto al pie de la letra: las ratios de co-ocurrencia entre palabras portan información semántica. Si X_wi,/X_wj, captura la relación entre dos palabras en el contexto de una tercera, entonces entrenar vectores que respeten esas ratios permite recuperar estructura semántica.

### Loss

Se minimiza la diferencia ponderada entre el producto de los vectores de palabra y contexto, y el logaritmo de las co-ocurrencias. El peso f(x_ij) da más importancia a co-ocurrencias frecuentes pero limita el impacto de valores extremadamente altos.

## Ventajas

- Usa información global del corpus
- Captura relaciones semánticas efectivamente
- Más interpretable que Word2Vec

## Limitaciones

- Como [[Word2Vec]], produce embeddings estáticos
- No captura polisemia

---

## Relación con otros conceptos

Ejemplo de [[Embeddings Estáticos]]. Alternativa a [[Word2Vec]]. Basado en [[Semántica Distribucional]]. Superado por [[Embeddings Contextuales]].
