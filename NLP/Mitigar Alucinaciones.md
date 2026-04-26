---
tags:
  - nlp
  - llm
  - safety
  - hallucinations
color: "#E67E22"
---

# Mitigar Alucinaciones

Técnicas para reducir la generación de información falsa o contradictoria por parte de los modelos.

## Funcionamiento

### Mejora de datos

- Usar datos de mayor calidad durante el preentrenamiento
- Filtrar fuentes poco confiables
- Verificar factualidad antes de incluir datos

### Mejora de arquitecturas

- Usar [[RAG]] para proporcionar contexto factual externo
- Incorporar mecanismos de verificación en el modelo

### Mejora de instrucciones

- Pedir al modelo que cite fuentes
- Incluir instrucciones explícitas para no inventar información
- Usar técnicas de few-shot con ejemplos verificados

### Mejora de post-procesamiento

- Verificar las respuestas con fuentes externas
- Filtrar respuestas que no son verificables

### Limitaciones

- Las alucinaciones son inherentes a la naturaleza predictiva de los modelos
- No existe solución perfecta

---

## Relación con otros conceptos

Aborda el problema de [[Alucinaciones]] en [[LLMs en general]]. Usa [[RAG]], [[RLHF]], y [[DPO]] como herramientas.
