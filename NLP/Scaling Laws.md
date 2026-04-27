---
tags:
  - nlp
  - llm
  - scaling
color: "#E67E22"
---

# Scaling Laws

Relaciones predecibles entre el tamaño del modelo, la cantidad de datos, el cómputo, y el rendimiento.

## Funcionamiento


### Hallazgo principal

Las scaling laws muestran que la loss baja de manera predecible cuando aumentamos tres cosas del entrenamiento: el número de parámetros, la cantidad de datos y el cómputo.

La idea importante es que los modelos grandes siguen mejorando si ese crecimiento viene acompañado por suficientes datos y suficiente entrenamiento. No alcanza con agrandar solo la red, porque si falta data o cómputo el modelo queda desaprovechado. Por eso, escalar bien no es solo hacer el modelo más grande, sino crecer en los tres ejes de forma balanceada.

### Chinchilla

El aporte de Chinchilla fue mostrar que muchos modelos grandes estaban subentrenados, o sea, tenían demasiados parámetros para la cantidad de tokens con la que habían sido entrenados. La conclusión fue que, para un presupuesto fijo, conviene usar más datos y un modelo algo más chico, en lugar de concentrar todo en un modelo enorme mal entrenado.

### Capacidades emergentes con escala

Al escalar mucho los modelos decoder-only como GPT-3 en parámetros, datos y cómputo, empiezan a aparecer capacidades de [[In-Context Learning]], resolver tareas nuevas a partir del prompt mismo, sin necesidad de reentrenar el modelo para cada caso.

En lugar de hacer fine-tuning específico, se le puede mostrar una instrucción sola zero-shot, una instrucción con un ejemplo one-shot, o con unos pocos ejemplos few-shot, y el desempeño mejora a medida que crece el tamaño del modelo.

### Implicaciones

- No hay un tamaño óptimo claro: más parámetros, más datos, más cómputo = mejor rendimiento
- La mejora es consistente y predecible
- Justifica la inversión en modelos cada vez más grandes

### Leyes específicas

- El error escala como una potencia del número de parámetros
- El error escala como una potencia de la cantidad de datos
- El error escala como una potencia del cómputo total

---

## Relación con otros conceptos

Base teórica del escalamiento de [[LLMs en general]]. Explica el surgimiento de [[Capacidades Emergentes]] y [[In-Context Learning]]. Justifica el desarrollo de [[GPT-2]], [[LLaMA]], y [[Mixture of Experts]].
