---
tags:
  - nlp
  - model-architectures
  - transformers
  - attention
color: "#2980B9"
---

# Queries, Keys y Values

Las tres matrices proyectadas desde los embeddings de entrada en el mecanismo de [[Self-Attention]].

## Concepto

Intuitivamente, estas tres matrices son tres miradas distintas sobre los mismos embeddings de entrada.

### Queries (Q)

Representan para cada token qué tipo de información está buscando en el resto de la secuencia. Es como la "pregunta" que realiza ese token.

### Keys (K)

Representan para cada token qué información puede ofrecer. Funcionan como una "etiqueta" contra la cual las queries se comparan para medir compatibilidad.

### Values (V)

Contienen la información que efectivamente se va a mezclar para construir la nueva representación contextual.

## Relación

Con Q y K se decide a quién mirar y cuánto, y con V se decide qué información tomar de esos tokens atendidos. Q y K sirven para calcular relevancia y V aporta el contenido que se combina en la salida.

## Atención vs Feed-Forward

El bloque de self-attention sirve para mezclar información entre tokens y decidir qué palabras son relevantes entre sí, pero por sí solo es básicamente una combinación ponderada de representaciones ya existentes.

La feed-forward se agrega después para transformar no linealmente la representación de cada token de manera independiente, permitiendo construir atributos más complejos y expresivos.

- **Atención:** comunica tokens entre sí
- **Feed-forward:** procesa y refina esa información en cada posición

Sin la feed-forward, el modelo tendría mucha menos capacidad para aprender transformaciones ricas capa a capa.

---

## Relación con otros conceptos

Componentes de [[Self-Attention]] y [[Multi-Head Attention]] en la arquitectura [[Transformers]].
