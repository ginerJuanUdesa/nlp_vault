---
tags:
  - nlp
  - model-training
  - embeddings
  - word2vec
color: "#27AE60"
---

# Negative Sampling

Técnica de entrenamiento eficiente que aproxima la función de pérdida de la red neuronal seleccionando un subconjunto de ejemplos negativos.

## Funcionamiento

### Problema

El problema de la loss original de [[Skip-gram]] (softmax original) es que el denominador suma sobre todo el vocabulario. Si el vocabulario tiene 100k palabras, en cada paso de entrenamiento hay que normalizar sobre 100k términos, lo que es extremadamente lento.

### Solución

Negative sampling reemplaza eso. En lugar de calcular la probabilidad sobre todo el vocabulario, transforma el problema de clasificación multiclase en un problema de clasificación binaria: para cada par real (palabra central, contexto), se eligen k palabras aleatorias y el modelo aprende a distinguir el par real de los falsos.

- Maximizar σ(c_cantadas · v_chacareras): que el par real tenga alta similitud
- Maximizar σ(-c_ruido · v_chacareras): que los pares falsos tengan baja similitud

En vez de actualizar 100k pesos, solo se actualizan k+1 por paso, haciendo el entrenamiento mucho más rápido.

### Proceso

1. Se elige un ejemplo positivo (pareja que debería tener alta probabilidad)
2. Se eligen k ejemplos negativos (parejas que deberían tener baja probabilidad)
3. Se actualizan solo los pesos de estas parejas

### Distribución de muestreo

Los ejemplos negativos se eligen según una distribución que favorece las palabras frecuentes pero no demasiado.

---

## Relación con otros conceptos

Técnica clave en el entrenamiento de [[Word2Vec]] (Skip-gram). Parte de [[Embeddings Estáticos]].
