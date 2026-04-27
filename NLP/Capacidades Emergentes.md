---
tags:
  - nlp
  - llm
  - emergent-behavior
color: "#E67E22"
---

# Capacidades Emergentes

Capacidades que aparecen de forma inesperada al escalar los modelos en tamaño, datos y cómputo.

## Características


No son programadas explícitamente. Aparecen como consecuencia de:
- Escalar el número de parámetros
- Aumentar el volumen de datos de preentrenamiento
- Incrementar el cómputo total de entrenamiento

### Ejemplos

- **In-Context Learning:** No existe en modelos pequeños. Al escalar suficientemente, el modelo empieza a responder a ejemplos incluidos en el prompt sin haber sido entrenado para ello.
- **Chain-of-Thought:** La capacidad de razonar paso a paso emerge en modelos grandes
- **Codificación interna de instrucciones:** Modelos grandes desarrollan la habilidad de interpretar y seguir instrucciones sin fine-tuning específico

### Hallazgo clave

La escalabilidad puede cambiar drásticamente las capacidades observables del modelo, no solo su rendimiento en métricas tradicionales.

---

## Relación con otros conceptos

Consecuencia directa de las [[Scaling Laws]] en [[LLMs en general]]. Relacionado con [[In-Context Learning]] y [[GPT-2]].
