---
tags:
  - nlp
  - llm
  - open-source
  - decoder
color: "#2980B9"
---

# LLaMA

**Large Language Model Meta AI** — familia de modelos de lenguaje de código abierto desarrollada por Meta.

## Funcionamiento


### Arquitectura

Decoder-only basado en [[Transformers]] con varias mejoras:
- **Pre-norm:** LayerNorm antes de cada sub-capas
- **SwiGLU:** Activación más eficiente que GeLU
- **RoPE:** Positional encodings rotacionales

### Tamaños

| Versión | Parámetros |
|---------|-----------|
| LLaMA-1 | 7B, 13B, 33B, 65B |
| LLaMA-2 | 7B, 13B, 70B |
| LLaMA-3 | 8B, 70B |

### Pipeline de entrenamiento (LLaMA 2)

- **Pretraining:** Se entrena Llama 2 como modelo base usando self-supervised learning (next token prediction) sobre un corpus de internet a gran escala.
- **Supervised Fine-Tuning (SFT):** Se toma Llama 2 y se lo entrena sobre ejemplos curados de conversaciones instrucción-respuesta para que aprenda a seguir instrucciones.
- **Human Feedback y Reward Models:** En paralelo, se recolectan datos de preferencias humanas, dado un prompt y dos respuestas, los humanos dicen cuál prefieren. Con esto se entrena un reward model que luego se usa con PPO para alinear el modelo.

### Impacto

- Código abierto permite investigación reproducible
- Generó un ecosistema de modelos derivados
- Demostró que modelos open-source pueden competir con modelos propietarios

---

## Relación con otros conceptos

Ejemplo de [[LLMs en general]] open-source. Usa [[Transformers]], [[Self-Attention]], [[KV Caching]], y [[Multi-Head Attention]]. Pipeline incluye [[Fine-Tuning]], [[Instruction Tuning]], y [[RLHF]].
