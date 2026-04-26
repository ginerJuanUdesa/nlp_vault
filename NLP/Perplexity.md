---
tags:
  - nlp
  - fundamentals
  - evaluation
  - language-models
color: "#27AE60"
---

# Perplexity

Métrica para evaluar la calidad de un modelo de lenguaje.

## Funcionamiento

### Definición

Medida de cuán bien las probabilidades predichas por un modelo de lenguaje se alinean con los datos reales. Es una métrica estándar para evaluar [[Modelos de Lenguaje]].

Si la secuencia W = {w1, w2, …, wn} se encontraba en el set de testeo, la probabilidad conjunta dadas las condiciones es la que el modelo asigna a esa secuencia completa.

La perplexidad se calcula a partir de los logaritmos de las probabilidades para evitar problemas numéricos como el underflow:

```
PP = 2^(-1/N * Σ log2 P(wi | w1...wi-1))
```

Intuitivamente, mide cuánto se "sorprende" el modelo al ver datos de prueba. Un modelo bueno asigna alta probabilidad a los datos reales, por lo que tiene baja perplexidad. Equivale al número efectivo de opciones que el modelo considera en cada paso.

### Interpretación

- **Perplexidad baja:** El modelo asigna alta probabilidad a los datos reales → buen modelo
- **Perplexidad alta:** El modelo se "sorprende" mucho con los datos → mal modelo

### Limitaciones

- No captura bien la calidad del texto generado
- No mide la coherencia semántica
- Se correlaciona mal con la percepción humana

---

## Relación con otros conceptos

Métrica de evaluación para [[Modelos de Lenguaje]], [[N-grams]], [[RNNs]], y [[Transformers]]. No es suficiente para evaluar [[LLMs en general]] modernos.
