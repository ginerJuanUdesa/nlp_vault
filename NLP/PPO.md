---
tags:
  - nlp
  - model-training
  - reinforcement-learning
color: "#8E44AD"
---

# PPO

**Proximal Policy Optimization** — algoritmo de optimización de políticas usado en aprendizaje por refuerzo, clave en el pipeline de [[RLHF]].

## Funcionamiento en RLHF


La dificultad es que el [[Reward Model]] solo devuelve un score escalar para una respuesta completa, pero no indica explícitamente qué token cambiar.

### Proceso

- Si una respuesta recibe reward alto, PPO aumenta la probabilidad de la secuencia que la produjo
- Si recibe reward bajo, la reduce
- Penaliza si el modelo se aleja demasiado del modelo de referencia (restricción proximal)

### Componentes

1. **Modelo actual:** el que se está optimizando
2. **Modelo de referencia:** versión fija del modelo (punto de partida)
3. **Reward Model:** da puntajes de calidad a las respuestas

### Problemas

- El modelo puede "engañar" al reward model
- Costoso computacionalmente
- Complejo de implementar

---

## Relación con otros conceptos

Parte de [[RLHF]] para alineación de [[LLMs en general]]. Usa [[Reward Model]] como señal. Reemplazado en parte por [[DPO]] que es más simple y estable.
