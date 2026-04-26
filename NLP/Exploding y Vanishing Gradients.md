---
tags:
  - nlp
  - model-architectures
  - sequence-models
  - gradients
color: "#2980B9"
---

# Exploding y Vanishing Gradients

Problemas de entrenamiento en [[RNNs]] al propagar gradientes a través del tiempo.

## Backpropagation Through Time

En una RNN, al entrenar con BPTT, el gradiente que llega a un estado lejano se obtiene como un producto de muchas derivadas encadenadas entre tiempos consecutivos.

### Vanishing Gradient

Si esos términos son menores que 1, el producto se hace cada vez más chico y el gradiente tiende a cero. Los pesos casi no se actualizan y la red no logra aprender dependencias largas.

### Exploding Gradient

Si los términos son mayores que 1, el producto crece demasiado, generando actualizaciones excesivas e inestables.

## Soluciones

### Gradient Clipping (exploding)

Si la norma del gradiente supera un umbral `θ`, se reescala manteniendo la misma dirección pero limitando la magnitud. Intuitivamente, el clipping acota el tamaño del paso y en vez de que el optimizador "salte" por una pendiente muy abrupta, avanza con pasos controlados.

### Truncated BPTT (vanishing)

No retropropagar el error a través de toda la secuencia sino solo sobre una ventana corta de pasos recientes. Hace más estable el entrenamiento, pero al ignorar los estados más lejanos el modelo deja de aprender relaciones entre elementos muy separados en el tiempo.

## Limitación

Estas soluciones son parches. La verdadera solución vino con [[LSTMs]] y luego con [[Transformers]].

---

## Relación con otros conceptos

Problema de [[RNNs]]. Motivación para [[LSTMs]] y [[Transformers]]. Relacionado con [[LayerNorm]] para estabilizar entrenamiento.
