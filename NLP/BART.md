---
tags:
  - nlp
  - model-architectures
  - transformers
  - encoder-decoder
color: "#2980B9"
---

# BART

**Bidirectional and Auto-Regressive Transformers** — modelo encoder-decoder que combina preentrenamiento generativo y reconstructivo.

## Funcionamiento


### Tareas de preentrenamiento

1. **Ruido en el input:** Se corrompe el texto de entrada (eliminación de tokens, permutación, etc.)
2. **Reconstrucción:** El decoder debe reconstruir el texto original a partir del texto corrupto

### Arquitectura

- Encoder bidireccional como [[BERT]]
- Decoder autoregresivo como [[GPT]]
- Combina lo mejor de ambos mundos

### Ventajas

- Puede generar texto (decoder)
- Entender contexto completo (encoder bidireccional)
- Robusto al ruido en la entrada

### Aplicaciones

- Resumen de texto
- Traducción automática
- Generación de texto

---

## Relación con otros conceptos

Modelo [[Seq2Seq]] basado en [[Transformers]]. Combina [[BERT]] (encoder) y [[GPT]] (decoder). Alternativa a [[T5]].
