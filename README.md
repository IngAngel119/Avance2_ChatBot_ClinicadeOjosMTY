# Avance de Proyecto 2 - Desarrollo de aplicaciones con Inteligencia Artificial

Modelo de texto con TF-IDF + Naive Bayes y componente visual preparado con ResNet50.

> **Nota:** El CSV contiene ejemplos de prueba. La CNN requiere imágenes oftalmológicas autorizadas y clasificadas. No se generan métricas sin datos reales.

## 1. Descripción del proyecto

- **Problema:** preguntas frecuentes y solicitudes de citas generan carga administrativa.
- **Objetivo:** responder consultas e identificar intenciones.
- **Usuarios:** pacientes y personal de la clínica.
- **Alcance:** orientación y solicitudes simuladas; sin agenda ni expedientes reales.
- **Flujo:** mensaje → preprocesamiento → clasificador → respuesta. Imagen → ResNet50 → clase y confianza.
- **Seguridad:** no diagnostica. Ante síntomas repentinos o lesiones, recomienda atención médica urgente.

## 2. Datos de texto

Se carga `dataset_intenciones_clinica.csv`, con 15 ejemplos por intención. Ampliar con frases variadas y datos no sensibles.

## 3. Preprocesamiento

Se normaliza el texto, se tokeniza con NLTK, se eliminan stopwords y se aplica stemming en español.

## 4. TF-IDF y Naive Bayes

TF-IDF convierte los mensajes en vectores y `MultinomialNB` clasifica las 13 intenciones. Se separan datos de entrenamiento y prueba.

## 5. Datos de imágenes

Usar imágenes **autorizadas** y etiquetas del conjunto original. Separar entrenamiento, validación y prueba por paciente para evitar filtraciones.

Estructura:

```text
dataset/
  train/clase_1/
  val/clase_1/
  test/clase_1/
