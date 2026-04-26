---
tags:
  - nlp
  - model-architectures
  - transformers
  - decoder
color: "#2980B9"
---

# GPT-2

GPT-2 fue un salto importante respecto de GPT-1 porque escaló en casi todas las dimensiones relevantes: aumentó mucho el tamaño del modelo (de 117M a 1.5B parámetros), usó más datos y mejor curados.

## Arquitectura

![[attachments/image130.png]]

Arquitectura decoder-only estándar de [[Transformers]] con [[Self-Attention]] causal.

## Sensitivity to local errors

Mide cuánto se deteriora el resultado global cuando se cometen errores pequeños en pasos individuales.

- El modelo es más sensible a errores locales al principio de la generación que al final
- Un error temprano pasa a formar parte del contexto para todos los pasos siguientes
- Un error tardío afecta menos porque quedan pocos tokens por generar

## Scale All You Need

La idea de "escala es todo lo que necesitas": si el modelo se vuelve lo suficientemente grande y se preentrena con una cantidad enorme de texto, empieza a resolver tareas sin necesidad de fine-tuning.

### Zero-shot
El modelo resuelve una tarea sin haber visto ejemplos resueltos de esa tarea. Solo recibe una instrucción.

### Few-shot
Se dan unos pocos ejemplos de cómo se hace la tarea antes de pedirle la respuesta. El modelo usa estos ejemplos como guía inmediata sin necesidad de reentrenar.

---

## Relación con otros conceptos

Evolución de [[GPT]]. Demuestra [[Scaling Laws]] y el surgimiento del [[In-Context Learning]] al escalar. Precursor de los [[LLMs en general]] modernos.
