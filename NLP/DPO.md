---
tags:
  - nlp
  - model-training
  - alignment
color: "#8E44AD"
---

# DPO

**Direct Preference Optimization** — alternativa a RLHF que optimiza directamente con datos de preferencias, sin entrenar un reward model explícito.

## Funcionamiento


### Idea central

En vez de aprender primero un score de reward y después hacer RL, DPO compara cuánto más probable hace el modelo actual a la respuesta buena respecto de la mala.

### Proceso

Para cada prompt se tienen dos respuestas, una elegida (y) y una rechazada (l). Ambas se pasan tanto por el modelo que se está entrenando (π_θ) como por un modelo de referencia (π_ref).

### Loss

Así, el entrenamiento empuja a que la policy π_θ aumente la probabilidad relativa de y y reduzca la de l, pero sin alejarse demasiado del modelo de referencia. El término π_ref actúa como ancla para evitar colapso.

Se mide la diferencia en log-probabilidad entre la respuesta preferida y la rechazada. Si este valor es grande, el modelo favorece mucho más al ejemplo bueno. Si es chico o negativo, aún no está separando bien los ejemplos.

### Ventajas

- No hace falta un reward model separado
- La señal de preferencia queda incorporada directamente en la comparación
- Más estable que RLHF con PPO
- Menos costoso computacionalmente

---

## Relación con otros conceptos

Alternativa a [[RLHF]] y [[PPO]]. Simplifica el pipeline de alignment eliminando la necesidad de [[Reward Model]]. Se aplica sobre modelos de [[LLMs en general]] después de [[Instruction Tuning]].
