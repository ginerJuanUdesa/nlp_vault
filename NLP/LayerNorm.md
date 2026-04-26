---
tags:
  - nlp
  - model-architectures
  - normalization
color: "#2980B9"
---

# LayerNorm

**Layer Normalization** — técnica de normalización que estabiliza el entrenamiento de redes profundas.

## Funcionamiento

![[attachments/image106.png]]

### Concepto

A diferencia de Batch Normalization que normaliza sobre el batch, LayerNorm normaliza sobre la dimensión de características de cada muestra individual.

### Proceso

1. Se calcula la media y varianza de las activaciones de cada capa
2. Se normalizan las activaciones restando la media y dividiendo por la desviación estándar
3. Se aplican parámetros aprendibles de escala y desplazamiento

### Ventajas

- No depende del tamaño del batch
- Funciona bien con secuencias de longitud variable
- Estabiliza el entrenamiento de redes profundas

---

## Relación con otros conceptos

Componente clave en [[Transformers]], [[BERT]], [[GPT]], y [[LLMs en general]]. Se aplica después de cada sub-capas de atención y feed-forward.
