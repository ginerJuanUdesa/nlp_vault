---
tags:
  - nlp
  - llm
  - overview
color: "#E67E22"
---

# LLMs en general

**Large Language Models** — modelos de lenguaje de gran escala que demuestran capacidades sorprendentes en tareas de NLP.

## Características

### ¿Qué los hace diferentes?

- **Escala:** Millones a billones de parámetros
- **Datos:** Entrenados en corpus masivos de texto
- **Capacidades:** No solo predicen texto, sino que siguen instrucciones, razonan, y generan contenido coherente

### Pipeline de entrenamiento

1. [[Pre Training]] en texto masivo
2. [[Fine-Tuning]] en tareas específicas
3. [[Instruction Tuning]] para seguir instrucciones
4. [[RLHF]] o [[DPO]] para alineación

### Arquitecturas

- [[Transformers]] decoder: [[GPT]], [[LLaMA]]
- [[Transformers]] encoder: [[BERT]], [[RoBERTa]], [[ELECTRA]]
- [[Transformers]] encoder-decoder: [[T5]], [[BART]]

### Desafíos

- [[Alucinaciones]]
- Sesgos
- Costo computacional
- Seguridad y ética

---

## Relación con otros conceptos

Término paraguas que incluye [[GPT]], [[BERT]], [[LLaMA]], y otros. Usa [[Scaling Laws]], [[Self-Attention]], [[KV Caching]], y [[Mixture of Experts]].
