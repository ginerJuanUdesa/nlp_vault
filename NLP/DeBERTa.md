---
tags:
  - nlp
  - model-architectures
  - encoder
  - transformers
  - microsoft
color: "#2980B9"
---

# DeBERTa

**Decoding-enhanced BERT with Disentangled Attention** — mejora de BERT y RoBERTa desarrollada por Microsoft que separa el contenido de la posición en la atención.

## Innovaciones Principales

### 1. Atención Desentrelazada (Disentangled Attention)

En lugar de mezclar contenido y posición en un solo vector como hacen BERT y RoBERTa, DeBERTa representa cada palabra con **dos vectores independientes**:

- **Vector de contenido:** qué dice la palabra
- **Vector de posición:** dónde está la palabra en la secuencia

Los pesos de atención se computan usando matrices desentrelazadas por separado sobre el contenido y las posiciones relativas. Esto permite al modelo aprender relaciones de posición de forma más eficiente.

### 2. Decodificador Mejorado con Máscara (Enhanced Mask Decoder)

Incorpora posiciones absolutas en la capa de decodificación para predecir los tokens enmascarados durante el preentrenamiento con [[Modelo de Lenguaje Enmascarado (MLM)]]. Esto mejora la capacidad del modelo de usar información posicional al completar palabras ocultas.

### 3. Entrenamiento Adversarial Virtual

Un método de entrenamiento adversarial aplicado durante el fine-tuning para mejorar la generalización del modelo.

## Resultados

- Con la mitad de los datos de entrenamiento que RoBERTa-Large, supera consistentemente en tareas NLU y NLG
- **DeBERTa-v2 (1.5B parámetros):** Superó el rendimiento humano en SuperGLUE por primera vez (89.9% vs 89.8%)
- El modelo ensemble de DeBERTa alcanzó 90.3% en SuperGLUE

## Ventajas

- Mayor eficiencia en el uso de datos de preentrenamiento
- La separación contenido-posición permite aprender relaciones posicionales más ricas
- Mejor generalización en tareas downstream

---

## Relación con otros conceptos

Mejora sobre [[BERT]] y [[RoBERTa]]. Usa el mismo esquema de [[Modelo de Lenguaje Enmascarado (MLM)]] con decodificador mejorado. Arquitectura [[Transformers]] encoder. Pipeline de [[Pre Training]] y [[Fine-Tuning]] para [[Transfer Learning]].
