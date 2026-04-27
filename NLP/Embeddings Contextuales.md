---
tags:
  - nlp
  - embeddings
  - contextual
color: "#27AE60"
---

# Embeddings Contextuales

El vector de una palabra depende de su contexto en la oración.

## Concepto


En cada instante `t`, el modelo combina la entrada actual con el estado oculto anterior para construir la representación. Esto permite que la misma palabra tenga vectores distintos según el contexto.

### Ejemplo
- "banco" financiero → vector distinto
- "banco" de plaza → vector distinto

## Ejemplos de modelos

- [[RNNs]]: hidden states como embeddings contextuales (unidireccional)
- [[LSTMs]]: Bi-LSTMs, contexto bidireccional
- [[ELMo]]: múltiples capas de Bi-LSTM combinadas
- [[BERT]]: Transformer encoder, atención bidireccional
- [[GPT]]: Transformer decoder, atención causal

## Ventajas

- **Resuelven polisemia:** Vector distinto según el contexto de uso
- **Capturan sintaxis y semántica:** Aprenden patrones del lenguaje automáticamente

## Limitaciones

- Modelos más grandes
- Requieren más recursos computacionales
- Necesitan preentrenamiento

## Detalles técnicos

- Usan [[Positional Encodings]] para preservar el orden de las palabras
- El embedding contextual de un token integra información de todos los tokens visibles

---

## Relación con otros conceptos

Evolución de [[Embeddings Estáticos]]. Generados por [[Transformers]], [[RNNs]], y [[LSTMs]]. Fundamentales para [[Transfer Learning]] y [[Fine-Tuning]].
