---
tags:
  - nlp
  - fundamentals
  - representation
color: "#27AE60"
---

# Representando Entidades

Cómo codificar entidades discretas y qué características deseables tienen las representaciones aprendidas.

## Codificación discreta

En el caso de que tengamos entidades discretas, podemos saber cuántos bits necesitamos para codificar todo el dominio, asignando un número a una entidad única. Si tenemos `n` entidades distintas en total, entonces vamos a necesitar `log₂(n)` bits para codificar todo el dominio de elementos con un número único.

### Problema

¿Qué pasa si no conocemos de antemano todos los objetos/elementos con sus respectivas variantes? Y más aún, qué pasa si los features no son discretos?

## Características deseables

Entonces vamos a querer aprender una representación a partir de los datos. Las características deseables son:

- **Compactas:** Ocupan poco espacio sin perder información esencial (dim reducida)
- **Densas:** La información está distribuida a lo largo de todas las componentes
- **Discriminativas:** Separan bien las distintas clases o factores de variación
- **Disentangled:** Diferentes dimensiones representan factores de variación independientes
- **Fáciles de manipular:** Soportan tareas posteriores
- **Robustas:** Resistentes al ruido y capaces de generalizar datos no vistos

## Embedding Model

Un Embedding Model transforma las entidades en vectores. Es una red neuronal que captura los aspectos importantes de las entidades según la necesidad de la tarea.

### Intuición general

Un espacio de embeddings es una representación comprimida, y lo que "comprime bien" depende de la función de loss:
- Si la loss penaliza errores fonéticos, el espacio va a aprender fonética
- Si penaliza errores de clasificación de sentimiento, va a aprender algo cercano a valencia emocional
- Los embeddings semánticos ([[Word2Vec]], [[GloVe]]) son el default porque la hipótesis distribucional resulta útil para muchas tareas downstream, pero no es la única geometría posible

---

## Relación con otros conceptos

Base de [[Representation Learning]] y [[Word Embeddings]]. Conduce a [[Embeddings Estáticos]] y [[Embeddings Contextuales]].
