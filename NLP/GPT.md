---
tags:
  - nlp
  - model-architectures
  - transformers
  - decoder
color: "#2980B9"
---

# GPT

**Generative Pre-trained Transformer** — familia de modelos decoder-only que conservan solo la parte decoder del Transformer original.

## Arquitectura


En vez de tener un encoder que construye una representación completa, los tokens de entrada se procesan directamente en el decoder. Usa self-attention causal: cada posición puede mirar solo a los tokens anteriores (y a sí misma), pero no a los futuros.

### Ventajas
- Arquitectura muy natural para generación de texto
- Reduce la cantidad de decisiones de modelado
- No se decide qué parte va al encoder y qué parte al decoder

### Desventaja principal
- No ven toda la secuencia de manera bidireccional como [[BERT]]
- Suelen ser menos naturales para tareas de comprensión que requieren contexto completo

## Entrenamiento

Se entrena con secuencias "perfectas" usando [[Teacher Forcing]]. Durante la generación, los errores se propagan porque el modelo no ve el ground truth.

## Generación

Genera texto palabra por palabra de forma autoregresiva, utilizando su conocimiento previo y el contexto proporcionado. Cada nueva palabra se selecciona en función de probabilidades calculadas sobre el vocabulario.

---

## Relación con otros conceptos

Arquitectura [[Transformers]] decoder-only. Precursor de [[GPT-2]], [[LLMs en general]], y [[In-Context Learning]]. Usa [[Self-Attention]] con [[Causal Masking]] y [[KV Caching]] para optimizar inferencia.
