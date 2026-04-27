---
tags:
  - nlp
  - model-architectures
  - encoder
  - transformers
color: "#2980B9"
---

# BERT

**Bidirectional Encoder Representations from Transformers** — modelo encoder-only que usa atención bidireccional para entender el contexto completo de cada token.

## Funcionamiento


### Tarea de preentrenamiento: MLM

**Masked Language Modeling:** Se oculta el 15% de los tokens de la entrada y el modelo debe predecirlos.

- 80% de las veces: token [MASK]
- 10% de las veces: token original (para que no aprenda que [MASK] siempre es una máscara)
- 10% de las veces: token aleatorio (para ruido)

### BERT Input Representation

En BERT, la representación de entrada de cada posición se construye como la suma de tres embeddings:

- **Token embedding:** Identifica qué token hay en esa posición
- **Position embedding:** Indica en qué lugar de la secuencia está
- **Segment embedding:** Distingue entre dos oraciones diferentes cuando se procesan juntas

### Ventaja clave

A diferencia de los [[Modelos de Lenguaje]] unidireccionales, BERT ve el contexto completo (izquierda y derecha) gracias a la arquitectura encoder del Transformer.

### Configurations

| Versión | Capas | Heads | Hidden | Parámetros |
|---------|-------|-------|--------|------------|
| BASE | 12 | 12 | 768 | 110M |
| LARGE | 24 | 16 | 1024 | 340M |

## Aplicaciones

- Clasificación de texto
- Análisis de sentimientos
- Named Entity Recognition
- Question answering

No se usa para generar texto.

---

## Relación con otros conceptos

Arquitectura encoder de [[Transformers]]. Precursor de [[RoBERTa]], [[ELECTRA]], [[DeBERTa]], y [[Embeddings Contextuales]]. Contraste con [[GPT]] (decoder-only). Base del [[Fine-Tuning]] moderno.
