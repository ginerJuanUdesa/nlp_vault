---
tags:
  - nlp
  - model-architectures
  - transformers
  - encoder-decoder
color: "#2980B9"
---

# Seq2Seq

**Sequence-to-Sequence** — arquitectura encoder-decoder que transforma una secuencia de entrada en una secuencia de salida de longitud variable.

## Funcionamiento

![[attachments/image35.png]]

### Concepto

Es una arquitectura pensada para tareas donde tanto la entrada como la salida son secuencias, incluso si tienen distinta longitud.

### Arquitectura

- **Encoder:** Lee la secuencia de entrada y la resume en su hidden-state final.
- **Decoder:** Usa esa representación para generar la secuencia de salida token a token.

### Aplicaciones

- Traducción automática
- Resumen de texto
- Question answering
- Chatbots

### Limitaciones

- La representación fija del encoder puede perder información
- Las [[RNNs]] originales tenían problemas con secuencias largas
- Los [[Transformers]] resolvieron estos problemas con [[Self-Attention]]

---

## Relación con otros conceptos

Arquitectura base de [[BART]], [[T5]], y [[Transformers]] encoder-decoder. Usa [[Attention]] para conectar encoder y decoder. Reemplazado por [[Transformers]] en la mayoría de aplicaciones.
