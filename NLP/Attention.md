---
tags:
  - nlp
  - model-architectures
  - attention
  - transformers
color: "#2980B9"
---

# Attention

Mecanismo que permite al modelo enfocarse en partes relevantes de la entrada al procesar cada posición.

## Funcionamiento

### Concepto general

El [[Mecanismo de Atención]] permite identificar qué partes de la entrada son más relevantes para una predicción, en lugar de depender solo de un único vector final. El modelo asigna un peso de atención a cada input o estado oculto según su importancia, y luego combina los inputs usando esos pesos.

No todas las palabras contribuyen igual, el modelo puede concentrarse en las más útiles para decidir la salida. Esto ayuda a reducir el cuello de botella, capturar mejor relaciones de largo alcance y además aporta cierta interpretabilidad, porque los pesos muestran a qué partes de la entrada el modelo se está fijando.

### Self-Attention en Transformers

El self-attention es el mecanismo propio de los Transformers que permite calcular, para cada token, cuánto debe atender a cada uno de los demás tokens. Por ejemplo, si tomamos la palabra "River" en una oración, el modelo compara su representación con la de todas las otras palabras para calcular una puntuación de atención.

Para eso, a partir de los embeddings de entrada se proyectan tres matrices: Q (queries), K (keys) y V (values).

### Tipos

- **Self-attention:** La entrada y la salida son la misma secuencia
- **Cross-attention:** La entrada y la salida son secuencias diferentes (ej: encoder-decoder)

### Componentes

- **Query:** Qué información se busca
- **Key:** Qué información se ofrece
- **Value:** La información que se mezcla

### Ventajas

- Permite capturar dependencias a larga distancia
- Se puede paralelizar completamente
- Proporciona interpretabilidad a través de los pesos de atención

---

## Relación con otros conceptos

Mecanismo base de [[Self-Attention]] y [[Multi-Head Attention]]. Reemplaza a [[RNNs]] y [[LSTMs]] en la arquitectura [[Transformers]].
