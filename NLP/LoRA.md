---
tags:
  - nlp
  - model-training
  - efficient-fine-tuning
color: "#4D7BCC"
---

# LoRA

**Low-Rank Adaptation** — técnica de adapter que aproxima la corrección de pesos como producto de dos matrices de bajo rango.

## Funcionamiento

![[attachments/image143.png]]

### Idea

Entonces con LoRA se reemplaza la multiplicación por `W` por `W + ΔW`, tal que `W` queda fijo y solo se entrena la corrección.

La idea es aproximar esa corrección ΔW como producto de dos matrices de bajo rango:

En LoRA no se modifican directamente los pesos pre-entrenados `W`, sino que se congelan y se aprende solo una corrección de bajo rango que se suma:

```
W' = W + ΔW ≈ W + A * B
```

- `W` → pesos originales (fijos, no se entrenan)
- `A` y `B` → matrices de bajo rango que se ajustan
- `r` → rango menor elegido (r << d)

### Ahorro de parámetros

En vez de entrenar `d²` parámetros de `ΔW`, solo se entrenan `A` y `B` que suman `2dr` parámetros. Con `r` mucho menor que `d`, el ahorro es drástico.

### Aplicación

Se aplica en varias capas del modelo: capas de atención y feed-forward.

## Ventajas

- Reduce los parámetros entrenables
- Minimiza overfitting
- Reduce tiempos de entrenamiento
- Permite aprendizaje multi-tarea compartiendo un solo modelo base

---

## Relación con otros conceptos

Variante de [[Adapters]] para fine-tuning eficiente de [[LLMs en general]]. Alternativa al [[Fine-Tuning]] completo. Complementa a [[Transfer Learning]].
