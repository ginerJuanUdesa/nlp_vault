---
tags:
  - nlp
  - embeddings
  - word2vec
  - static
color: "#27AE60"
---

# Skip-gram

Variante de [[Word2Vec]] que predice el contexto dadas las palabras.

## Funcionamiento


Skip-gram toma la palabra central y aprende a predecir las palabras de contexto alrededor. La ventana de contexto es un hiperparámetro. El modelo tiene dos matrices de embeddings:

- `v` (vectores de palabras centrales)
- `c` (vectores de contexto)

### Intuición

Para predecir que "guitarra" aparece cerca de "bajo", queremos que el producto `v · c` sea grande (apunten en la misma dirección).

### Probabilidad

La probabilidad se calcula con un softmax sobre todo el vocabulario.

### Arquitectura

La entrada es el one-hot de la palabra central, un vector de 1×|V|. Al multiplicar por `W` (|V|×d), como el input es one-hot, simplemente se extrae la fila correspondiente (lookup).

- **Projection layer:** Embedding de la palabra central (1×d)
- **Output:** Una rama por cada posición de contexto, cada rama multiplica por `C` (d×|V|) y aplica softmax
- **Parámetros entrenables:** `W` y `C`

### Entrenamiento

Arranca con vectores aleatorios, itera palabra por palabra en el corpus, y ajusta los vectores para maximizar la probabilidad de las palabras que efectivamente aparecen en la ventana. Al final, palabras que aparecen en contextos similares terminan con vectores similares porque tuvieron que predecir las mismas palabras vecinas.

### Resultado

Al finalizar, puede usarse `W` como matriz de embeddings, `C^t`, o el promedio de ambas.

### Optimización

Usa [[Negative Sampling]] para evitar ajustar todos los pesos del vocabulario en cada paso.

---

## Relación con otros conceptos

Parte de [[Word2Vec]] y [[Embeddings Estáticos]]. Basado en [[Semántica Distribucional]]. Se optimiza con [[Negative Sampling]].
