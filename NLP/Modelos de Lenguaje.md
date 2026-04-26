---
tags:
  - nlp
  - fundamentals
  - language-models
color: "#27AE60"
---

# Modelos de Lenguaje

Modelos que asignan una probabilidad a secuencias de palabras.

## Funcionamiento

### Concepto básico

Dada una secuencia de palabras `w1, w2, ..., wn`, el modelo calcula:

```
P(w1, w2, ..., wn) = Π P(wi | w1, ..., wi-1)
```

### Evolución

1. **Modelos n-gram:** Solo miran los n-1 tokens anteriores
2. **Modelos neuronales:** Usan redes para capturar dependencias a largo plazo
3. **Transformers:** Usan atención para capturar dependencias globales

### Aplicaciones

- Generación de texto
- Corrección ortográfica
- Traducción automática
- Reconocimiento de voz

### Limitaciones de modelos simples

- Los n-gram no capturan dependencias a largo plazo
- Los modelos neuronales son más expresivos pero requieren más datos

---

## Relación con otros conceptos

Base teórica de [[GPT]], [[BERT]], y [[LLMs en general]]. Se implementa con [[RNNs]], [[LSTMs]], y [[Transformers]]. Se evalúa con [[Perplexity]].
