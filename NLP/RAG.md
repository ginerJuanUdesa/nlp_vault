---
tags:
  - nlp
  - llm
  - retrieval
color: "#E67E22"
---

# RAG

**Retrieval-Augmented Generation** — ofrecerle al modelo generativo la opción de buscar información externa en el momento para mejorar su respuesta.

## Funcionamiento

### Proceso
1. Se recibe una consulta del usuario
2. Se busca información relevante en una base de datos externa
3. El contexto recuperado se incluye en el prompt del modelo
4. El modelo genera la respuesta usando tanto su conocimiento como el contexto

### Beneficios

- **Conocimiento actualizado:** No está limitado al corte del entrenamiento
- **Contexto específico:** Se adapta a la pregunta concreta
- **Personalizable:** Acceso a documentos personales o internos

### Limitaciones

- Requiere infraestructura de búsqueda
- Depende de la calidad de los documentos recuperados
- Latencia adicional por la búsqueda

---

## Relación con otros conceptos

Complemento para [[LLMs en general]] que mitiga [[Alucinaciones]] al proporcionar contexto factual. Se relaciona con [[Mitigar Alucinaciones]] y [[Destilación]].
