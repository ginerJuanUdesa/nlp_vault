---
tags:
  - nlp
  - embeddings
  - word-representation
  - term-context
color: "#27AE60"
---

# Term-Context Matrix

Alternativa a [[Word2Vec]] que captura co-ocurrencias de forma global.

## Limitación de Word2Vec

Word2Vec aprende ejemplo por ejemplo: cada par (palabra central, contexto) es un paso de entrenamiento. Si el corpus crece, la cantidad de pares crece proporcionalmente y cada uno requiere su propia iteración.

## Matriz Term-Context

Una alternativa es capturar la misma información de forma global con una matriz de tamaño |V| × |V|, donde cada celda cuenta cuántas veces dos palabras co-ocurren dentro de una ventana.

### Ventajas

- Se recorre el corpus una sola vez y se acumula todo en la matriz
- Si el corpus crece, las celdas se actualizan pero el tamaño de la matriz no cambia

### Información semántica

La matriz ya contiene información semántica: palabras con distribuciones de co-ocurrencia similares tienen filas similares. Cada fila es la representación de una palabra.

### Problema

Con vocabularios grandes esto genera vectores de altísima dimensionalidad (|V|), esparsos y costosos de almacenar.

### Solución

Reducir la dimensionalidad para comprimir cada fila en un vector denso y compacto (por ejemplo, 300 dimensiones en lugar de |V|) usando SVD.

---

## Relación con otros conceptos

Base teórica de [[GloVe]]. Alternativa a [[Word2Vec]] y [[Skip-gram]]. Parte de [[Embeddings Estáticos]].
