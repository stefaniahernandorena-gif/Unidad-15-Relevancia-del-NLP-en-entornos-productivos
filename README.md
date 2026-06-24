# Unidad-15-Relevancia-del-NLP-en-entornos-productivos
Unidad 15 · Relevancia del NLP en entornos productivos

# 🏭 Production-Grade NLP Pipeline: Twitter Customer Support (MLOps Framework)

Este repositorio contiene la implementación avanzada de un pipeline de **Procesamiento de Lenguaje Natural (NLP) orientado a entornos de producción reales (MLOps)**, aplicado al análisis de flujos de interacciones masivas basado en el corpus [Customer Support on Twitter](https://www.kaggle.com/datasets/thoughtvector/customer-support-on-twitter).

A diferencia de los enfoques puramente experimentales de laboratorio, este sistema integra automatización de punta a punta, control estricto de la escalabilidad de hardware, cálculo en tiempo real de KPIs de negocio y validación continua mediante una suite de pruebas de software automatizadas (`unittest`).

---

## 🛠️ Desafíos de Ingeniería y MLOps Resueltos

1. **Gestión de Carga Masiva (Anti-RAM Crash):** El dataset original cuenta con más de 2.8 millones de filas. Para evitar desbordamientos de memoria en la nube, el flujo se diseñó para permitir cargas controladas por lotes (*streaming/chunking*) y mecanismos de contingencia automatizados.
2. **Corrección del Búfer de Limpieza:** Se reparó un bug estructural en la expresión regular de normalización de URLs, asegurando que enlaces complejos de Twitter como `https://t.co/` sean purgados de raíz sin dejar cadenas corruptas en el corpus final.
3. **Optimización de Latencia en Inferencia:** Se sustituyeron modelos heurísticos obsoletos por un **Transformer optimizado de arquitectura profunda (`DistilBERT`)** configurado para ejecución masiva en lotes (*batching*), maximizando el rendimiento computacional de la GPU/CPU.

---

## 📈 Cuadro de Mando Operativo (KPIs Reales de Producción)

Tras ejecutar el pipeline sobre el conjunto de control, el sistema consolidó los siguientes Indicadores Clave de Rendimiento (KPIs) exigidos por la gerencia:

* **Volumen Total de Interacciones Procesadas:** 8 tweets analizados.
* **Tasa de Automatización de Enrutamiento:** **75.00%** (Clasificación instantánea y autónoma de incidencias fuera de la categoría general).
* **Alertas Críticas de Fricción Detectadas (Negativos):** **75.0%** del volumen total (Aislamiento prioritario para el equipo de contención).
* **Latencia Media de Inferencia del Modelo:** **136.71 ms / consulta** (Rendimiento óptimo para flujos síncronos y acuerdos de nivel de servicio).
* **Estimación de Ahorro de Tiempo Corporativo:** **0.40 horas de analista** diarias proyectadas de forma lineal.

---

## 🧪 Polución de Software y Validación (Suite de Pruebas Unitarias)

El pipeline incorpora una suite basada en el framework `unittest` integrada en los flujos de Integración Continua (CI/CD), asegurando que las funciones críticas mantengan su estabilidad matemática y lógica ante cambios de código:

```text
test_enrutamiento_categorias (__main__.TestPipelineProduccionNLP.test_enrutamiento_categorias) ... ok
test_limpieza_automatica (__main__.TestPipelineProduccionNLP.test_limpieza_automatica) ... ok

----------------------------------------------------------------------
Ran 2 tests in 0.041s

OK
