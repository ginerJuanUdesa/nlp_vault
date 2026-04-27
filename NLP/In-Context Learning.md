---
tags:
  - nlp
  - llm
  - inference
color: "#E67E22"
---

# In-Context Learning

Capacidad de un LLM de aprender a realizar una nueva tarea sin modificar sus pesos, simplemente observando ejemplos incluidos en el prompt.

## Funcionamiento


Al escalar mucho los modelos decoder-only como GPT-3 en parámetros, datos y cómputo, empiezan a aparecer capacidades de in-context learning.

### Modalidades

| Modalidad | Ejemplos en prompt | Descripción |
|-----------|-------------------|-------------|
| **Zero-shot** | 0 | Solo la instrucción |
| **One-shot** | 1 | Un ejemplo + nueva instrucción |
| **Few-shot** | varios | Varios ejemplos + nueva instrucción |

### Características

- No requiere fine-tuning
- El modelo usa los ejemplos como guía inmediata
- El desempeño mejora con ejemplos adicionales en el prompt
- Los modelos más grandes rinden mejor en benchmarks usando solo contexto

---

## Relación con otros conceptos

Capacidad emergente de los [[LLMs en general]] al escalar ([[Scaling Laws]]). Aparece en [[GPT]] y [[GPT-2]] al aumentar parámetros. Relacionado con [[Capacidades Emergentes]].
