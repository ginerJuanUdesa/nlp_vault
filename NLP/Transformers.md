---
tags:
  - nlp
  - model-architectures
  - transformers
color: "#2980B9"
---

# Transformers

Arquitectura revolucionaria basada en mecanismos de atención que reemplazó a las RNNs como modelo estándar para NLP.

## Funcionamiento


### Arquitectura

- **Encoder:** Procesa la secuencia de entrada y produce representaciones contextuales
- **Decoder:** Genera la secuencia de salida de forma autoregresiva
- **Self-Attention:** Cada token puede atender a todos los demás tokens
- **Feed-Forward:** Transformación no lineal aplicada a cada token independientemente

### Componentes clave

1. **Multi-Head Attention:** Múltiples cálculos de atención en paralelo
2. **Positional Encoding:** Información posicional agregada a los embeddings
3. **Layer Normalization:** Estabiliza el entrenamiento
4. **Residual Connections:** Permiten flujos de gradiente

### Codificación posicional sinusoidal

Para introducir la información posicional, esta técnica a cada posición p de la secuencia se le asigna un vector posicional donde:

- En dimensiones pares se usa: `sin(p / 10000^(2i/d_model))`
- En las impares: `cos(p / 10000^(2i/d_model))`

Esto da al modelo la capacidad de aprender a relacionar posiciones relativas, ya que para cualquier desplazamiento fijo k, PE(p+k) se puede representar como una transformación lineal de PE(p).

### Ventajas sobre RNNs

- Procesamiento paralelo completo
- Captura dependencias a cualquier distancia
- Escala mejor con el hardware moderno

---

## Relación con otros conceptos

Base de [[BERT]], [[GPT]], [[T5]], [[BART]], [[LLaMA]], y todos los [[LLMs en general]]. Usa [[Self-Attention]], [[Multi-Head Attention]], [[Positional Encodings]], y [[LayerNorm]].
