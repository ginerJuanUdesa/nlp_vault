---
tags:
  - nlp
  - model-training
  - alignment
  - reinforcement-learning
color: "#8E44AD"
---

# RLHF

**Reinforcement Learning from Human Feedback** — procedimiento para ajustar un modelo de lenguaje usando preferencias humanas como señal de entrenamiento.

## Proceso


### 1. Generación y Ranking

Dado un mismo prompt, el modelo genera varias respuestas. Un humano compara esas respuestas y las ordena.

### 2. Reward Modelling

Se entrena un modelo para evaluar respuestas según las preferencias humanas. No genera texto, sino que devuelve un score.

### 3. Optimización con PPO

Se ajusta el modelo de lenguaje original para maximizar el reward esperado, con penalización KL para evitar desviación excesiva del modelo base.

## Formulación

En la formulación de RLHF, se define:
- **Policy (πθ):** El modelo de lenguaje que se está optimizando
- **Reward (r):** El score dado por el reward model
- **Penalización KL:** Evita que el modelo se desvíe demasiado del modelo base

El objetivo es maximizar E[r] - β * KL(πθ || π_ref), donde β controla la fuerza de la penalización.

## Problemas

- Costoso y lento (requiere humanos para etiquetar)
- Introduce sesgos (preferencias humanas pueden ser inconsistentes)
- Sensible a errores del reward model
- Complejidad computacional de PPO

---

## Relación con otros conceptos

Pipeline de alignment para [[LLMs en general]]. Componentes: [[Reward Model]] y [[PPO]]. Alternativa más simple: [[DPO]]. Se aplica después de [[Instruction Tuning]] y [[Fine-Tuning]]. Central en [[LLaMA]].
