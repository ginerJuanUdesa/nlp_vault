---
tags:
  - nlp
  - model-architectures
  - transformers
  - positional-encoding
color: "#2980B9"
---

# Positional Encodings

Mecanismo que agrega información de posición a los embeddings de entrada para que el modelo sepa el orden de los tokens.

## Funcionamiento


### ¿Por qué son necesarios?

[[Transformers]] no son secuenciales como [[RNNs]] o [[LSTMs]]. Todos los tokens se procesan en paralelo. Sin información posicional, el modelo no sabría el orden de las palabras.

### Tipos

#### Positional Encoding absoluto (original)

Se agregan vectores sinusoidales de frecuencias diferentes a cada posición:

```
PE(pos, 2i) = sin(pos / 10000^(2i/d))
PE(pos, 2i+1) = cos(pos / 10000^(2i/d))
```

#### RoPE (Rotary Positional Embeddings)

Se aplican rotaciones a los vectores de query y key según la posición. Permite generalizar a longitudes de secuencia no vistas durante el entrenamiento.

### Ventajas

- Permiten paralelización completa
- Capturan relaciones posicionales
- Generalizan a secuencias más largas que las vistas en entrenamiento

---

## Relación con otros conceptos

Componente esencial de [[Transformers]], [[BERT]], [[GPT]], [[LLaMA]], y [[LLMs en general]]. Reemplaza la noción de posición temporal en [[RNNs]].
