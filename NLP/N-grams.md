---
tags:
  - nlp
  - fundamentals
  - language-models
  - n-grams
color: "#27AE60"
---

# N-grams

Modelos de lenguaje basados en la hipótesis de Markov: la probabilidad de una palabra depende solo de las n-1 palabras anteriores.

## Funcionamiento

### Concepto

Un modelo n-gram asume que la probabilidad de una palabra depende solo de las n-1 palabras precedentes:

```
P(w_i | w_1, ..., w_{i-1}) ≈ P(w_i | w_{i-n+1}, ..., w_{i-1})
```

### Ejemplos

- **Unigram (n=1):** Cada palabra es independiente
- **Bigram (n=2):** La probabilidad depende de la palabra anterior
- **Trigram (n=3):** La probabilidad depende de las dos palabras anteriores

### Conteo

Surge el problema: ¿cómo contamos cuántas veces aparece una frase en el lenguaje? Antes del Deep Learning, tomábamos un corpus representativo de "el lenguaje" y contábamos literalmente las palabras. Deberíamos haber definido de antemano nuestro vocabulario.

El problema que surge es que tenemos que almacenar todas las subcadenas existentes y su frecuencia de aparición. Además, es probable que un par (h, w) no exista en todo mi corpus. El vocabulario y las probabilidades que aprende el modelo solo serán útiles si el corpus de entrenamiento es lo suficientemente grande y representativo.

Dado que es probable que (h, w) no exista, una solución posible es achicar el contexto, generando más redundancia, ya que trivialmente es menos restrictivo. Esto también simplifica el almacenamiento de conteo, por ejemplo en caso de un 5-gram se puede reducir a trigrams o bigrams.

### Limitaciones

- No capturan dependencias a largo plazo
- El espacio de n-grams crece exponencialmente con n
- Muchos n-grams no aparecen en los datos de entrenamiento (problema de sparse data)
- No pueden generalizar a palabras similares (basados en conteo exacto)

### Suavizado

Técnicas para asignar probabilidad a n-grams no vistos:
- Laplace smoothing
- Kneser-Ney smoothing

---

## Relación con otros conceptos

Modelo básico de [[Modelos de Lenguaje]]. Precursor de los modelos neuronales ([[RNNs]], [[Transformers]]). Se evalúa con [[Perplexity]].
