---
tags:
  - nlp
  - transformer
  - attention
color: "#3498DB"
---

# Self-Attention

El self-attention es el mecanismo propio de los Transformers que permite calcular, para cada token, cuánto debe atender a todos los demás tokens de la secuencia.

## Funcionamiento


A partir de los embeddings de entrada se proyectan tres matrices:

- **Queries (Q):** qué información está buscando cada token en el resto de la secuencia
- **Keys (K):** qué información puede ofrecer cada token ("etiqueta" contra la cual se comparan las queries)
- **Values (V):** la información que efectivamente se mezcla para construir la nueva representación contextual

### Cálculo de atención

1. Se calculan los scores de atención mediante el producto interno Q·K^T
2. Se escala por √d_k
3. Se aplica softmax para obtener pesos de atención
4. Se multiplica por V para obtener la salida


### ¿Por qué escalar por √d_k?

Cuando la dimensión d_k es grande, el producto interno tiende a valores extremos que la softmax colapsa a distribuciones muy concentradas. Esto hace que los gradientes se hagan casi cero. Escalar por √d_k mantiene la varianza de los scores aproximadamente en 1, evitando la saturación de la softmax.

### Atención vs Feed-Forward

El bloque de self-attention mezcla información entre tokens y decide qué palabras son relevantes entre sí. La feed-forward se agrega después para transformar no linealmente la representación de cada token de manera independiente.

- **Atención:** comunica tokens entre sí
- **Feed-forward:** procesa y refina esa información en cada posición

Sin el feed-forward, la atención solo haría combinaciones lineales y el modelo perdería poder expresivo.

---

## Relación con otros conceptos

Componente central de la arquitectura [[Transformers]]. Se combina en [[Multi-Head Attention]] para permitir múltiples subespacios de atención en paralelo. Con [[Causal Masking]] permite generación autoregresiva en decoders ([[GPT]]). Con [[KV Caching]] optimiza la inferencia.
