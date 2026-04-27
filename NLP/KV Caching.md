---
tags:
  - nlp
  - llm
  - inference
  - optimization
color: "#E67E22"
---

# KV Caching

Técnica de optimización para la inferencia de modelos de lenguaje que almacena los valores de Key y Value calculados previamente.

## Funcionamiento


### Problema

En generación autoregresiva, en cada paso se calcula la atención sobre todos los tokens anteriores. Esto implica re-calcular los mismos Key y Value una y otra vez.

### Solución

En vez de re-calcular los Keys y Values de los tokens anteriores en cada paso, se almacenan en caché y se reutilizan. Solo se calculan los nuevos Key y Value del token actual.

### Ahorro

- Sin caché: O(n²) operaciones en cada paso
- Con caché: O(n) operaciones en cada paso

### Limitaciones

- Requiere memoria adicional para almacenar los valores en caché
- Solo beneficia la inferencia, no el entrenamiento

---

## Relación con otros conceptos

Optimización clave para la inferencia de [[GPT]], [[LLaMA]], y [[LLMs en general]] decoder. Mejora la eficiencia de [[Generación de Texto]].
