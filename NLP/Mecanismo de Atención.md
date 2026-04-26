---
tags:
  - nlp
  - model-architectures
  - attention
  - mechanism
color: "#2980B9"
---

# Mecanismo de Atención

Mecanismo que permite identificar qué partes de la entrada son más relevantes para una predicción.

## Concepto

En lugar de depender solo de un único vector final (como el último hidden state de una RNN en [[Seq2Seq]]), el mecanismo de atención permite al modelo concentrarse selectivamente en las partes más útiles de la entrada.

### Intuición

No todas las palabras contribuyen igual. El modelo puede concentrarse en las más relevantes para decidir la salida. Esto ayuda a:

- Reducir el cuello de botella de la representación fija
- Capturar mejor relaciones de largo alcance
- Aportar interpretabilidad (los pesos muestran dónde se fija el modelo)

## Implementación Básica

Para calcular qué palabras son más importantes, a cada embedding de la secuencia se le asigna un score mediante una pequeña red feed-forward:

El score mide cuán relevante es ese token para la predicción. Luego se aplica softmax sobre todos los scores para obtener los pesos de atención que suman 1. Finalmente, con esos pesos se construye una representación de contexto como combinación ponderada de los embeddings.

## Ventajas sobre RNN

- Acceso directo a cualquier posición de la secuencia (no depende de propagación secuencial)
- Pesos aprendidos adaptativamente por cada ejemplo (no fijos)
- Paralelizable (no hay dependencia temporal)

---

## Relación con otros conceptos

Precursor conceptual de [[Self-Attention]] en [[Transformers]]. Se usa en [[Seq2Seq]] con atención. Base para [[Multi-Head Attention]].
