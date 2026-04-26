---
tags:
  - nlp
  - fundamentals
  - embeddings
  - word-representation
color: "#27AE60"
---

# Representación Simbólica del Conocimiento

Representación y manipulación de símbolos para modelar y razonar sobre información textual.

## One-Hot Encoding

Cada palabra se convierte a un vector con un "1" en la posición i-ésima (asociada únicamente a esa palabra) y "0" en todas las demás. El problema es que cada palabra vive en su propia dimensión ortogonal, haciendo que todas las palabras sean equidistantes entre sí y el espacio no capture ninguna relación semántica.

## Conjuntos Semánticos

Grupos de palabras o frases que comparten un significado común, utilizados para modelar el conocimiento mediante relaciones como hipónimos (de lo específico a lo general).

## Limitaciones

- **Falta de matices:** Las relaciones entre palabras son binarias. "Proficiente" y "bueno" no son intercambiables en todos los contextos ("es un proficiente cirujano" ≠ "es un buen tipo"). El recurso no captura esa gradación.
- **Cobertura incompleta:** Construidos manualmente por humanos, siempre desactualizados. Jerga, neologismos, tecnicismos nuevos directamente no existen.
- **Subjetividad y creación laboriosa:** Dos personas pueden no estar de acuerdo en si dos palabras son sinónimas. Construir y mantener estos recursos es caro en tiempo humano.
- **Recurso estático:** Una vez construido, no se actualiza solo. El lenguaje evoluciona pero el recurso queda fijo. Grave en redes sociales donde el léxico cambia rápido.
- **Inexactitud en la similitud:** Trata todas las palabras dentro de un conjunto como igualmente similares. "Feliz" y "contento" quedan al mismo nivel que "feliz" y "eufórico".

## Conclusión

El hilo común de todas estas limitaciones es que la representación simbólica depende de conocimiento humano explícito, y por eso hereda todos sus sesgos, gaps y costos.

---

## Relación con otros conceptos

Precursor superado por [[Embeddings Estáticos]] ([[Word2Vec]], [[GloVe]]) y [[Embeddings Contextuales]]. Motivación para [[Representation Learning]].
