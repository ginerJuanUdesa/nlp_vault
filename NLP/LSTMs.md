---
tags:
  - nlp
  - model-architectures
  - sequence-models
color: "#2980B9"
---

# LSTMs

**Long Short-Term Memory** — tipo especial de RNN diseñada para resolver el problema del vanishing gradient.

## Funcionamiento

![[attachments/image120.png]]
![[attachments/image23.png]]
![[attachments/image87.png]]
![[attachments/image107.png]]

### Concepto

La LSTM es una variante de las [[RNNs]] diseñada para que la red pueda recordar información importante durante más tiempo y no la vaya perdiendo a medida que avanza la secuencia.

Para eso, además del estado oculto ht (hidden state de ese instante) incorpora un estado de celda ct, que funciona como una memoria más estable y está pensado específicamente para transportar información relevante a lo largo del tiempo.

La clave es que esa memoria no se actualiza de manera caótica, sino mediante compuertas que controlan el flujo de información:

- **Forget gate:** Decide qué parte de la memoria anterior ct-1 conviene conservar y qué parte olvidar.
- **Input gate:** Decide qué información nueva, extraída de la entrada actual xt y del estado oculto previo ht-1, vale la pena incorporar al estado de celda ct.
- **Output gate:** Decide qué parte del estado de celda se va a exponer como hidden state ht.

### Célula y compuertas

### Ventajas sobre RNNs

- Mantiene información relevante a largo plazo
- Controla explícitamente qué se recuerda y qué se olvida
- Mitiga el problema del vanishing gradient

### Variantes

- **Bi-LSTM:** Dos LSTMs procesan la secuencia en ambas direcciones
- **Stacked LSTMs:** Varias capas de LSTM apiladas

## Limitaciones

- Aún procesa secuencialmente (no paralelizable)
- Computacionalmente más costosa que RNNs simples
- Superada por [[Transformers]] en la mayoría de tareas

---

## Relación con otros conceptos

Mejora de [[RNNs]]. Usada en [[ELMo]] para embeddings contextuales. Superada por [[Transformers]] y [[Self-Attention]] en tareas de NLP modernas.
