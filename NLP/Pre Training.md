---
tags:
  - nlp
  - fundamentals
  - pretraining
color: "#27AE60"
---

# Pre Training

Fase inicial de entrenamiento de un modelo de lenguaje en grandes volúmenes de texto sin supervisión.

## Funcionamiento


### Proceso

1. Se recopila un corpus enorme de texto (libros, Wikipedia, web, etc.)
2. Se tokeniza el texto
3. Se entrena el modelo para predecir tokens (masked en [[BERT]], next-token en [[GPT]])
4. El modelo aprende patrones gramaticales, semánticos, y del mundo

### Tareas de preentrenamiento

- **Masked Language Modeling (MLM):** Predecir tokens enmascarados (BERT, [[RoBERTa]])
- **Next-token Prediction:** Predecir el siguiente token ([[GPT]], [[LLaMA]])
- **Replaced Token Detection:** Detectar tokens reemplazados ([[ELECTRA]])

### Objectivos

- Aprender representaciones ricas del lenguaje
- Capturar conocimiento factual
- Aprender a generalizar

---

## Relación con otros conceptos

Primer paso del pipeline: Pre Training → [[Transfer Learning]] → [[Fine-Tuning]] → [[Instruction Tuning]]. Base de [[LLMs en general]] ([[GPT]], [[BERT]], [[LLaMA]]).
