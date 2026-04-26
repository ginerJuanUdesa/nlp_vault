---
tags:
  - nlp
  - model-architectures
  - encoder
  - transformers
color: "#2980B9"
---

# RoBERTa

**Robustly Optimized BERT Pretraining Approach** — versión optimizada de [[BERT]] que elimina NSP y usa más datos y batch size.

## Funcionamiento

### Cambios respecto a BERT

RoBERTa elimina la tarea de [[Modelo de Lenguaje Enmascarado (MLM)]] de next sentence prediction y entrena más tiempo con más datos:

1. **Sin NSP:** El Next Sentence Prediction no aporta información
2. **Más datos:** Se entrena con mucho más texto
3. **Más batch size:** Mejora la convergencia
4. **Entrenamiento más largo:** Más épocas y steps
5. **Sin masking dinámico:** Los tokens enmascarados se fijan antes del forward pass

### Resultados

- Supera a BERT en la mayoría de benchmarks
- Requiere el mismo modelo base
- Mejora viene de cambios en el proceso de preentrenamiento

## Ventajas

- Más robusto
- Mejor rendimiento en tareas downstream
- Sin cambios arquitectónicos necesarios

---

## Relación con otros conceptos

Mejora de [[BERT]]. Mismo pipeline de [[Pre Training]] y [[Fine-Tuning]]. Usado en [[Transfer Learning]].
