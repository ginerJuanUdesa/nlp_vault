---
tags:
  - nlp
  - embeddings
  - contextual
  - transformer
color: "#27AE60"
---

# ELMo

**Embeddings from Language Models** — primer modelo en producir embeddings contextuales usando un Language Model entrenado con Bi-LSTMs.

## Funcionamiento

![[attachments/image12.png]]
![[attachments/image96.png]]

### Arquitectura

- Usa Bi-LSTMs para procesar texto en ambas direcciones
- Cada capa del Bi-LSTM captura un nivel diferente de abstracción
- Las representaciones de todas las capas se combinan para formar el embedding contextual final

### ¿Qué hace que ELMo sea diferente?

- **Contextual:** El mismo token tiene vectores distintos según su contexto en la oración
- **Multi-capas:** Aprovecha información de todos los niveles del modelo
- **Sin reentrenamiento:** Se calcula una vez y se usa como input para otros modelos

### Entrenamiento

Se entrena como un [[Modelos de Lenguaje]]: predice la siguiente palabra dado el contexto.

## Ventajas

- Primero en resolver la polisemia con embeddings dinámicos
- Mejora significativamente tareas downstream (NER, clasificación, etc.)

## Limitaciones

- Ventana de contexto limitada por las LSTMs
- Computacionalmente costoso

---

## Relación con otros conceptos

Puente entre [[Embeddings Estáticos]] y [[Embeddings Contextuales]]. Precursor de [[BERT]] y [[Transformers]]. Usa [[LSTMs]] como base. Parte de [[Representation Learning]].
