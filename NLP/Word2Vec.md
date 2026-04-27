---
tags:
  - nlp
  - embeddings
  - word-representation
  - static
color: "#27AE60"
---

# Word2Vec

Familia de técnicas para aprender embeddings de palabras entrenando redes neuronales sobre texto.

## Funcionamiento


### CBOW - Continuous Bag of Words

- Usa palabras de contexto para predecir la palabra central ([[CBOW]])
- Toma `c` palabras alrededor de un target y las promedia
- Reduce la dimensionalidad con una capa oculta más pequeña
- Más rápido de entrenar

### Skip-gram

- Usa la palabra central para predecir las palabras de contexto ([[Skip-gram]])
- Para cada token, se elige un contexto y se intenta predecir
- Funciona mejor con datasets pequeños y vocabularios grandes

### Window Size

Define cuántas palabras alrededor de cada token se usan para generar los ejemplos de entrenamiento.

## Detalles de entrenamiento

### Negative Sampling

En vez de ajustar todos los pesos, se eligen un pequeño número de ejemplos negativos al azar del vocabulario. Esto permite entrenar con vocabularios enormes.

### Subsampling

Las palabras muy frecuentes (artículos, preposiciones) aportan poca información semántica. Se eliminan aleatoriamente una fracción de estas palabras frecuentes durante el entrenamiento.

## Resultados

- Los vectores aprendidos capturan similitudes semánticas
- Permiten analogías relacionales (Rey - Hombre + Mujer = Reina)
- No consideran el contexto específico de cada uso (embedding estático)

---

## Relación con otros conceptos

Ejemplo de [[Embeddings Estáticos]]. Basado en [[Semántica Distribucional]]. Complementado por [[GloVe]] y superado por [[Embeddings Contextuales]] ([[BERT]], [[ELMo]]).
