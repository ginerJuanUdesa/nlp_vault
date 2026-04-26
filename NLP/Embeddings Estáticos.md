---
tags:
  - nlp
  - embeddings
  - static
color: "#27AE60"
---

# Embeddings Estáticos

Cada palabra tiene un único vector fijo, independiente del contexto.

## Evolución

### Representación simbólica

Antes se utilizaban representaciones discretas:
- **One-hot encoding:** vector de longitud igual al vocabulario con 1 en la posición de la palabra y 0 en todas las demás
- **Conjuntos semánticos:** grupos de palabras que comparten significado común

### Limitaciones de la representación simbólica

- **Falta de matices:** las relaciones entre palabras son binarias
- **Cobertura incompleta:** construidos manualmente, siempre desactualizados
- **Subjetividad:** dos personas pueden no estar de acuerdo en sinónimos
- **Recurso estático:** no se actualizan solos ante evolución del lenguaje
- **Inexactitud en similitud:** todas las palabras dentro de un conjunto son igualmente similares entre sí

### Representaciones continuas

Las palabras se representan como vectores densos en un espacio continuo que captura relaciones semánticas. Son compactos, dimensión fija, y reducen la dimensionalidad respecto al one-hot.

## Ejemplos

- [[Word2Vec]]: CBOW y Skip-gram
- [[GloVe]]: co-ocurrencia global

## Ventajas

- Menos costosos computacionalmente
- Vectores fijos y precalculados

## Limitaciones

- **Polisemia:** Un solo embedding para todas las acepciones
  - Ej: "banco" (financiero / de plaza) → mismo vector
- No capturan contexto dinámico

---

## Relación con otros conceptos

Contraste con [[Embeddings Contextuales]] ([[ELMo]], [[BERT]], [[GPT]]). Basados en [[Semántica Distribucional]]. Parte de [[Representation Learning]].
