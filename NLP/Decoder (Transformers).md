---
tags:
  - nlp
  - model-architectures
  - transformers
  - decoder
color: "#2980B9"
---

# Decoder (Transformers)

Componente del Transformer original que genera secuencias de salida de forma autoregresiva.

## Arquitectura

El decoder tiene tres subcapas por bloque (vs dos en el [[Encoder (Transformers)]]):

1. **Self-attention causal** (masked): Solo ve tokens anteriores
2. **Cross-attention:** Atiende a la salida del encoder
3. **Feed-forward network (FFN)**

## Self-Attention Causal

A diferencia del encoder que ve todos los tokens, el decoder usa una máscara triangular superior para que cada posición solo pueda atender a posiciones anteriores o iguales. Esto es esencial para el entrenamiento autoregresivo: al predecir el token t, no puede "ver" los tokens t+1 en adelante.

## Cross-Attention

La segunda subcapa usa:
- **Queries:** Provenientes del propio decoder
- **Keys y Values:** Provenientes del encoder

Esto permite que el decoder consulte la representación completa de la entrada en cada paso de generación.

## Generación

Durante la inferencia, el decoder genera un token a la vez. Cada token generado se agrega a la secuencia de entrada del decoder para el siguiente paso. Para hacer esto eficiente se usa [[KV Caching]] para no re-computar los cálculos de los tokens ya generados.

## Uso en Modelos Modernos

El decoder del Transformer original se usa en arquitecturas encoder-decoder como [[T5]] y [[BART]]. Los modelos [[Decoder-Only]] ([[GPT]], [[LLaMA]]) simplifican esta arquitectura eliminando el encoder y la cross-attention.

---

## Relación con otros conceptos

Parte de la arquitectura original de [[Transformers]]. Base de [[T5]] y [[BART]]. Versión simplificada en [[Decoder-Only]]. Usa [[Causal Masking]] y [[KV Caching]].
