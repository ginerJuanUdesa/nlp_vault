---
tags:
  - nlp
  - model-architectures
  - transformers
  - decoder
color: "#2980B9"
---

# Decoder-Only

Modelos que conservan solo la parte decoder del Transformer original.

## Arquitectura

En vez de tener un encoder que construye una representación completa del input y un decoder que genera la salida, hay un único bloque que recibe una secuencia de tokens y aprende a predecir el siguiente token.

### Self-Attention Causal

Cada posición puede mirar solo a los tokens anteriores (y a sí misma), pero no a los futuros dado que el modelo se entrena y genera de forma autoregresiva, token por token.

## Ventajas

- **Natural para generación:** Si la tarea consiste en continuar, completar, responder o producir secuencias, alcanza con modelar "dado lo anterior, cuál viene después"
- **Excelente para:** Chat, escritura, resumen generativo, código, QA generativo
- **Unificación:** Todo puede formularse como next-token prediction, simplificando el preentrenamiento
- **Menos decisiones de modelado:** No hay que decidir qué parte va al encoder, qué parte al decoder, cómo conectarlos

## Desventajas

- Usan máscara causal, no ven toda la secuencia de manera bidireccional como [[BERT]]
- Suelen ser menos naturales para tareas puramente de comprensión/clasificación si no se reformulan como generación

---

## Relación con otros conceptos

Arquitectura de [[GPT]], [[GPT-2]], [[LLaMA]], y la mayoría de los [[LLMs en general]] modernos. Usa [[Self-Attention]] con [[Causal Masking]] y [[KV Caching]].
