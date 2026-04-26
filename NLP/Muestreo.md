---
tags:
  - nlp
  - generation
  - sampling
color: "#E67E22"
---

# Muestreo

Estrategias para seleccionar tokens durante la generación de texto.

## Funcionamiento

### Greedy Search

Siempre se elige el token con mayor probabilidad. Produce texto coherente pero repetitivo y predecible.

### Top-k Sampling

Se seleccionan solo los k tokens más probables y se re-normaliza la distribución sobre ellos. Elimina tokens improbables pero puede incluir tokens de baja calidad si k es grande.

### Top-p (Nucleus) Sampling

Se seleccionan los tokens mínimos necesarios cuya probabilidad acumulada alcance p. Más flexible que top-k porque el tamaño del conjunto varía según la distribución.

### Temperature Scaling

Se divide la distribución de logits por la temperatura antes del softmax:
- T < 1: distribución más concentrada
- T > 1: distribución más uniforme

### Beam Search

Se mantienen b candidatas en cada paso, expandiendo todas y manteniendo solo las b más probables. Balance entre calidad y diversidad.

---

## Relación con otros conceptos

Parte de [[Generación de Texto]] en [[GPT]], [[LLaMA]], y [[LLMs en general]]. Afecta la calidad de salida y [[Alucinaciones]].
