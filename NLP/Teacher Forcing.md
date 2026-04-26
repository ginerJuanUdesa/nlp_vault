---
tags:
  - nlp
  - model-training
  - pre-training
  - teacher-forcing
color: "#8E44AD"
---

# Teacher Forcing

Técnica de entrenamiento donde, en cada paso temporal, se le da al modelo la entrada verdadera del dataset (en vez de su propia salida previa) como input para el siguiente paso.

## Funcionamiento

Durante el entrenamiento, el modelo recibe siempre la secuencia de tokens correctos como entrada en cada paso, forzándolo a aprender la relación correcta entre inputs y outputs.

### Exposición Bias

Es el gap entre entrenamiento e inferencia. Durante el entrenamiento con teacher forcing, el modelo siempre ve los tokens correctos. Durante la generación, ve sus propias predicciones, que pueden contener errores que se acumulan paso a paso.

## Aplicaciones

Usado en [[RNNs]], [[LSTMs]], y [[Transformers]] durante preentrenamiento. Es fundamental en el entrenamiento de [[GPT]] y modelos [[Seq2Seq]].

---

## Relación con otros conceptos

Técnica usada en el preentrenamiento de [[Transformers]], [[RNNs]], y [[LSTMs]]. Relacionado con [[Pre Training]] y [[Fine-Tuning]].
