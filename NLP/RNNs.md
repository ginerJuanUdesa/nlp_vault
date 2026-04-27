---
tags:
  - nlp
  - model-architectures
  - sequence-models
color: "#2980B9"
---

# RNNs

**Redes Neuronales Recurrentes** — arquitectura que procesa secuencias paso a paso manteniendo un estado oculto que se actualiza en cada instante.

## Funcionamiento


### Características

Las Redes Neuronales Recurrentes están diseñadas específicamente para trabajar con datos secuenciales. Tienen la capacidad de "recordar" la información de pasos anteriores.

- **Conexiones recurrentes:** La salida de la capa oculta en el paso t se reinyecta como entrada en el paso t+1. Este "loop" hacia sí misma es lo que permite que la red mantenga un estado interno (memoria) que resume todo lo visto hasta el momento.
- **Estado oculto como memoria:** El hidden state ht acumula información de todos los inputs o tokens previos, no solo del anterior/contexto fijo. Funciona como un "resumen comprimido" de la secuencia pasada, condicionando cómo se procesa cada nuevo input.
- **Procesamiento secuencial:** Los datos se procesan token a token, en orden. Cada paso combina el input actual xt con el estado previo ht-1 para producir ht. El orden está codificado implícitamente en el hecho de que procesan secuencialmente.
- **Pesos compartidos:** Los mismos pesos se usan en todos los pasos temporales, lo que permite generalizar a secuencias de longitud variable sin aumentar los parámetros.

### Backpropagation Through Time

Los gradientes se propagan a través de los pasos temporales. Esto puede llevar a problemas de vanishing/exploding gradients.

### Aplicaciones

- Traducción automática
- Reconocimiento de voz
- Predicción de la siguiente palabra
- Análisis de sentimientos

## Limitaciones

Las RNN tienen dos limitaciones profundas que se vuelven especialmente determinantes en generación de texto con la arquitectura autoregresiva:

1. **No paralelizan:** El procesamiento secuencial impone que para computar ht se necesita ht-1, que a su vez necesita ht-2, y así hasta h0. Esto significa que durante el entrenamiento no se pueden procesar múltiples pasos en paralelo, limitando severamente la velocidad.

2. **No propagan bien información a larga distancia:** Conocido como [[Exploding y Vanishing Gradients]]. Aunque la RNN pueda guardar teóricamente toda la secuencia en su hidden state, en la práctica la información de los pasos más antiguos se diluye y el modelo olvida lo que ocurrió al principio de la secuencia.

## Evolución

Las [[LSTMs]] y las [[Transformers]] resuelven estas limitaciones.

---

## Relación con otros conceptos

Precursor de [[LSTMs]] y [[Transformers]]. Usado en [[Modelos de Lenguaje]] tempranos. [[ELMo]] usa Bi-LSTMs. Reemplazado por [[Self-Attention]] en modelos modernos.
