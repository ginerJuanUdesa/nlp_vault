---
tags:
  - nlp
  - generation
  - sampling
color: "#E67E22"
---

# Generación de Texto

Proceso de producir texto token por token de forma autoregresiva.

## Funcionamiento

### Proceso
1. Se da un prompt inicial
2. El modelo predice la distribución de probabilidad sobre el vocabulario
3. Se selecciona un token según la estrategia de muestreo
4. El token se agrega al contexto y se repite

### Estrategias de muestreo

- **Greedy:** Se elige siempre el token más probable
- **Top-k:** Se elige solo entre los k tokens más probables
- **Top-p (Nucleus):** Se elige entre los tokens cuyo累计 probabilidad alcance p
- **Beam Search:** Se mantienen los mejores b beams en cada paso

### Temperature

Parámetro que controla la aleatoriedad:
- Temperature baja → distribución más concentrada (respuestas más predecibles)
- Temperature alta → distribución más uniforme (respuestas más diversas)

---

## Relación con otros conceptos

Capacidad principal de [[GPT]], [[LLaMA]], y [[LLMs en general]] decoder. Se optimiza con [[KV Caching]]. Afecta por [[Alucinaciones]] y [[Mitigar Alucinaciones]].
