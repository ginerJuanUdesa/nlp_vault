---
tags:
  - nlp
  - model-architectures
  - transformers
  - encoder
color: "#2980B9"
---

# Encoder (Transformers)

Componente del Transformer que procesa la secuencia de entrada y produce representaciones contextuales.

## Arquitectura


El encoder está formado por `N` bloques iguales apilados, donde cada uno tiene dos subcapas principales:

1. **Multi-head self-attention**
2. **Feed-forward network (FFN)**

### Flujo

La entrada al encoder es la suma del embedding estático del token y el [[Positional Encodings]]. Esa representación va pasando capa por capa como hidden state:

- **Self-attention:** Cada token se re-representa en función de todos los demás tokens
- **FFN:** Refina esa representación de manera independiente para cada posición
- **Residual connections + LayerNorm:** Después de cada subcapa, preservan información y estabilizan el entrenamiento

## Hiperparámetros

| Hiperparámetro | Descripción | BERT Base | BERT Large |
|---------------|-------------|-----------|------------|
| **num_hidden_layers** | Profundidad del modelo | 12 | 24 |
| **hidden_size** | Dimensión de cada token (d_model) | 768 | 1024 |
| **max_position_embeddings** | Longitud máxima de secuencia | 512 | 512 |
| **num_attention_heads** | Cabezas de atención | 12 | 16 |
| **intermediate_size** | Tamaño de la FFN interna | 3072 | 4096 |
| **hidden_act** | Función de activación | GELU | GELU |

## Modificables sin reentrenar

- Dropout
- Uso de caché
- Longitud efectiva de entrada menor que la máxima
- Recortar capas (se conserva desde las primeras hacia atrás)

## No modificables sin reentrenar

- hidden_size
- num_attention_heads
- intermediate_size
- Compatibilidad entre dimensiones

---

## Relación con otros conceptos

Parte de la arquitectura [[Transformers]]. Base de [[BERT]], [[RoBERTa]], [[ELECTRA]], y [[T5]] (lado encoder). Usa [[Multi-Head Attention]] y [[LayerNorm]].
