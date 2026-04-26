---
tags:
  - nlp
  - fundamentals
  - evaluation
color: "#27AE60"
---

# Métricas

Medidas cuantitativas para evaluar el rendimiento de modelos de NLP.

## Métricas comunes

### Perplexity

Mide la incertidumbre del modelo sobre los datos de prueba. Se usa principalmente para evaluar [[Modelos de Lenguaje]].

### Exactitud (Accuracy)

Proporción de predicciones correctas sobre el total. Útil para clasificación.

### Precisión, Recall y F1

- **Precisión:** De las predichas como positivas, cuántas son realmente positivas
- **Recall:** De las realmente positivas, cuántas se predijeron correctamente
- **F1:** Media armónica de precisión y recall

### BLEU

Métrica para evaluar traducción automática. Compara n-grams del texto generado con las referencias.

### ROUGE

Métrica para evaluar resumen de texto. Mide la superposición de n-grams, secuencias, y pares de palabras.

---

## Relación con otros conceptos

[[Perplexity]] para [[Modelos de Lenguaje]]. BLEU y ROUGE para [[Generación de Texto]]. F1 para clasificación.
