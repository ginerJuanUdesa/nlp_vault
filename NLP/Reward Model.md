---
tags:
  - nlp
  - model-training
  - reinforcement-learning
color: "#8E44AD"
---

# Reward Model

Modelo que aprende a determinar con un score qué tan buena es una respuesta, basado en preferencias humanas.

## Funcionamiento


Reward modeling es la etapa en la que se entrena un modelo para evaluar respuestas según preferencias humanas. No genera texto como el LLM principal, sino que devuelve un puntaje.

### Proceso de entrenamiento

1. **SFT:** Se toma un prompt y un humano escribe una respuesta demostración
2. **Generación:** Para un mismo prompt, el modelo SFT genera varias respuestas distintas
3. **Ranking:** Un humano ordena esas respuestas de mejor a peor
4. **Entrenamiento:** El reward model aprende a reproducir ese ranking asignando scores

### Uso

El reward model puntúa respuestas candidatas para guiar la optimización en [[RLHF]].

### Limitaciones

- Requiere datos etiquetados por humanos (costoso y lento)
- Si el modelo aprende a "engañar" al reward model, genera respuestas sin sentido con alta puntuación

---

## Relación con otros conceptos

Componente esencial de [[RLHF]] y [[PPO]]. Alternativa eliminada por [[DPO]] que no necesita reward model explícito. Se aplica en el pipeline de [[LLaMA]] y [[LLMs en general]].
