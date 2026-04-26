---
tags:
  - nlp
  - model-architectures
  - transformers
  - encoder
color: "#2980B9"
---

# ELECTRA

Modelo encoder-only como [[BERT]] pero con tarea de preentrenamiento distinta: en vez de MLM es **discriminativo**.

## Funcionamiento

![[attachments/image129.png]]
![[attachments/image4.png]]
![[attachments/image40.png]]

### Problema con MLM

Primero, un MLM recibe una secuencia con algunos tokens ocultos y los reemplaza. Solo usa como objetivo de entrenamiento esas posiciones enmascaradas (15%), ignorando las otras 85%. Esto significa que en cada paso, solo una fracción de la secuencia produce gradiente.

### Arquitectura de entrenamiento

ELECTRA propone una tarea de preentrenamiento distinta al MLM clásico:

1. **Generador (MLM):** Recibe una secuencia con tokens enmascarados y propone reemplazos
2. **Discriminador (ELECTRA):** Recibe la secuencia con los reemplazos del generador y debe detectar qué tokens fueron sustituidos

La ventaja de este esquema es que el discriminador recibe supervisión en **todas las posiciones** de la secuencia y no solo en el 15% enmascarado.

### Ventajas sobre BERT

- El discriminador recibe supervisión en **todas las posiciones** de la secuencia, no solo en el 15% enmascarado
- Aprende mejor con menos datos y parámetros
- Más eficiente computacionalmente en tareas downstream

### Entrenamiento conjunto

A medida que el generador mejora, los reemplazos se vuelven más plausibles y la tarea del discriminador se vuelve más difícil, obligándolo a aprender representaciones más finas.

Los dos modelos se entrenan juntos minimizando la suma ponderada de sus respectivas losses.

## Aplicaciones

Las mismas que [[BERT]]: clasificación, análisis de sentimientos, NER. No se usa para generar texto.

---

## Relación con otros conceptos

Variante de [[BERT]] con mejor eficiencia en preentrenamiento. Arquitectura encoder de [[Transformers]]. Se usa en [[Fine-Tuning]] para tareas downstream.
