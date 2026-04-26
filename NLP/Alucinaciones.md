---
tags:
  - nlp
  - llm
  - failures
color: "#E67E22"
---

# Alucinaciones

Situaciones donde un modelo genera texto que carece de sentido o tiene información factual errónea, aunque parezca fluido y arraigado en el contexto.

## Tipos

| Tipo | Descripción |
|------|-------------|
| **Intrínseca** | La salida contradice directamente el material de entrada |
| **Extrínseca** | El contenido no puede ser verificado ni contradicho por la fuente |

## Conceptos relacionados

### Fidelidad

Mide cuánto respeta la salida a la fuente dada. Maximizar la fidelidad busca minimizar la alucinación intrínseca.

### Facticidad

Mide si lo dicho es verdad en el mundo real. Puede diferir de la fidelidad dependiendo del "hecho" definido.

## Causas

- **Datos de entrenamiento:** Información incorrecta o contradictoria
- **Naturaleza de tareas creativas:** Fomentan divergencia

## Mitigación

Para mitigar las alucinaciones se puede actuar en varios niveles:

- **Nivel de datos:** Mejorar la calidad de los datos de entrenamiento y de los datos usados para retrieval
- **Nivel de arquitectura:** Usar mecanismos que obliguen al modelo a basarse en fuentes externas ([[RAG]])
- **Nivel de generación:** Ajustar parámetros de muestreo, usar técnicas de verificación
- **Nivel de post-procesamiento:** Verificar la salida contra la fuente antes de presentarla

---

## Relación con otros conceptos

Problema clave de los [[LLMs en general]]. Se aborda en [[Mitigar Alucinaciones]] mediante mejora de datos, arquitecturas, y [[RLHF]]. Relacionado con [[Destilación]] al transferir conocimiento con fidelidad.
