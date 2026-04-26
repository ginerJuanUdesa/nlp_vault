---
tags:
  - nlp
  - model-architectures
  - encoder
  - pretraining
color: "#2980B9"
---

# Modelo de Lenguaje Enmascarado (MLM)

Tarea de preentrenamiento usada por [[BERT]], [[RoBERTa]], y [[DeBERTa]].

## Funcionamiento

Los modelos de lenguaje enmascarado se preentrenan ocultando aleatoriamente algunos tokens de una oración y pidiéndole al modelo que los prediga usando el contexto restante.

### Bidireccionalidad

Como el modelo puede mirar tanto a izquierda como a derecha del token oculto, aprende representaciones bidireccionales, muy útiles para tareas de comprensión como clasificación, análisis de sentimientos o reconocimiento de entidades.

### Loss

Durante el entrenamiento, la secuencia completa se procesa normalmente pero la pérdida se calcula solo sobre las posiciones enmascaradas.

## Estrategia de Masking

Se selecciona aleatoriamente un 15% de los tokens para que el modelo los prediga. Pero esos tokens no siempre se reemplazan igual:

- **80%:** Se cambia por [MASK]
- **10%:** Se cambia por un token aleatorio
- **10%:** Se deja igual aunque también se use como objetivo

### ¿Por qué esta mezcla?

Evita que el modelo dependa demasiado del símbolo [MASK], que no aparece en fine-tuning o inferencia. Obliga al modelo a aprender representaciones más robustas.

## Datos de Preentrenamiento

El preentrenamiento original de BERT se hizo sobre BooksCorpus y English Wikipedia, para combinar texto narrativo y texto enciclopédico.

## Variantes

- **RoBERTa:** Elimina la tarea de next sentence prediction y entrena más tiempo con más datos
- **Enfoques avanzados:** Enmascaran tokens contiguos en lugar de posiciones aisladas para volver la tarea más realista y difícil

---

## Relación con otros conceptos

Tarea de [[Pre Training]] para [[BERT]], [[RoBERTa]]. Contraste con el preentrenamiento causal de [[GPT]] ([[Decoder-Only]]).
