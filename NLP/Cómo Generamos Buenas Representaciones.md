---
tags:
  - nlp
  - fundamentals
  - representation
color: "#27AE60"
---

# Cómo Generamos Buenas Representaciones

Principios para aprender representaciones útiles a partir de datos sin etiquetar.

## Condiciones

Generamos buenas representaciones cuando:

### Aprovechamos datos sin etiquetar

En lugar de depender de labels humanos, usamos la estructura inherente de los datos. La pregunta guía: tengo millones de datos, ¿cómo extraigo señal útil de ellos solos?

### Definimos una tarea pretexto bien diseñada

El output tiene que ser una transformación programática del input. La red aprende representaciones útiles porque se ve forzada a predecir, reconstruir o contrastar aspectos del propio input. Si la tarea es trivial, la representación es pobre.

### Logramos invariancia y sensibilidad selectiva

Una buena representación es:
- **Robusta** a variaciones irrelevantes (ruido, orden, rotaciones)
- **Sensible** a lo que importa (identidad del objeto, semántica)

Es el balance entre no sobreajustar a detalles superficiales y no perder información crítica.

### El resultado es transferible

Si la representación es genuinamente buena, debería funcionar en múltiples tareas específicas con poco fine-tuning. Que rinda bien en varias es evidencia de que capturó estructura real.

### Es computacionalmente eficiente

El vector tiene que producirse en un forward pass rápido y tener dimensión razonable. Una representación que tarda horas en computarse no es práctica aunque sea perfecta en calidad.

---

## Relación con otros conceptos

Marco general para [[Representation Learning]], [[Pre Training]], y [[Transfer Learning]]. Aplica a [[Word Embeddings]], [[Embeddings Estáticos]], y [[Embeddings Contextuales]].
