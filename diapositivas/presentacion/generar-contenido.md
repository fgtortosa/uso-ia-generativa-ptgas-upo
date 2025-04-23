---
title: Uso de la inteligencia artificial generativa para el PTGAS de la Universidad Pablo de Olavide, de Sevilla - Generar contenido
author: Paco García Tortosa. Servicio de Informática - Universidad de Alicante
date: 2025-4-21
marp: true
tags:
  - CharlaIA
---

## Consideraciones iniciales
- La IA generativa puede ser una ayuda para las tareas del día a día del colectivo PTGAS de la Universidad de Olavide
- Es una herramienta de apoyo, **necesita ser supervisada**
- Como se usa en la nube, hay que evitar el uso de datos personales o de información sensible
- Es buena en tareas lingüísticas, no en razonamiento ni matemáticas (esto está cambiando rápidamente)

---

## Conceptos

**Prompt**: Texto con el que inicia la conversación. 

---

## Conceptos

**Prompt**

1. Hay que detallar el tipo de salida que se desea y toda aquella información que sea relevante (contexto). 
2. Si la salida que se desea es compleja, comenzar con una aproximación al problema para a continuación ir añadiendo la complejidad. 
3. En algunos casos puede ser interesante utilizar modelos con capacidad de razonamiento, por su capacidad de estructurar la tarea. **Para estos modelos, es útil dar instrucciones paso a paso o pedirles que "piensen en voz alta" (Chain-of-Thought).**

---

## Conceptos

**Contexto**

La información inicial y la recibida durante la conversación. Normalmente el contexto es temporal, la herramienta lo almacena durante algún tiempo y luego lo pierde.

---

## Conceptos

**Multimodalidad**

Se refiere a los distintos tipos de información con los que se puede alimentar a un modelo. Los modelos normales son de tipo "texto a texto". Cuando un modelo es multimodal permite normalmente el uso de texto, pero también de imágenes, audio, etc. Normalmente los modelos que permiten entradas de imagen son los llamados modelos de *visión*.

---

## Conceptos

**Razonamiento**

Algunos modelos pueden descomponer tareas complejas en pasos lógicos, planificar y seguir una estrategia. Esto es útil para problemas que requieren análisis detallado o seguir instrucciones precisas.

---

## Modelos que podemos usar
1. Claude
2. ChatGPT
3. Mistral
4. Gemini

---

### Claude
- Modelo de Anthropic
- Genera texto. Con buscador web
- Buen modelo para tareas de programación. Posee **buenas capacidades de razonamiento**
- Hay que registrarse para usarlo, en [https://claude.ai](https://claude.ai)

---

### ChatGPT
- Modelo de OpenAI
- Genera texto e imágenes. Con buscador web
- Es un buen modelo para tareas de razonamiento y en general para cualquier otro tipo de tarea, **especialmente en su versión de pago (GPT-4)**
- Hay que registrarse en [https://chatgpt.com](https://chatgpt.com)

---

### Mistral
- Modelo de Mistral (único modelo europeo)
- Genera texto e imágenes. Con agente para búsquedas
- Funciona bastante bien en multimodalidad. Buena capacidad para realizar traducciones entre idiomas europeos
- Hay que registrarse en [https://chat.mistral.ai/](https://chat.mistral.ai/)

---

### Google Gemini
- Genera texto e imágenes. Con buscador web
- Se puede usar sin registrarse desde una cuenta de *Gmail*. Para acceder: [https://gemini.google.com/](https://gemini.google.com/)
- Ha mejorado mucho últimamente, recomendado para tareas que necesiten un contexto muy grande (grandes documentos)

---

## Ejemplo práctico 1: Creación de una página web para un evento

Transformación de información de un cartel a página web estructurada

---

### Obtención de la información inicial

1. La información que nos proporcionan está en un cartel del propio evento
2. Todos los modelos nos van a obligar a registrarnos
3. Cada modelo puede dar una respuesta distinta
4. Cada vez que se le pregunta al modelo también puede dar una respuesta distinta (*esta inteligencia artificial es generativa*)
5. Utilizaremos en el ejemplo la IA Generativa de Mistral

---

### Pasos para el ejemplo

1. Registrarnos o loguearnos en Mistral: [https://chat.mistral.ai/](https://chat.mistral.ai/)
2. Descargar el documento de: [https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png](https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png)
3. Subir la imagen a la herramienta, utilizando el icono del clip que hay en la parte izquierda

---

### Transcripción inicial

Acercamiento inicial al problema, usando el modelo sin indicaciones específicas:

**Prompt**: *Transcribe el contenido del documento*

---

### Resultado de la transcripción

El resultado corresponde a la transcripción de los textos que contiene el cartel en el mismo orden en que aparecen en la imagen:
- Nombre de la jornada
- Fecha de la charla
- Descripción de los ponentes
- Lugar y hora del evento
- Coordinación
- Financiación

---

### Transformación de la información

Queremos **transformar la información** para que tenga un orden adecuado al uso que queremos darle.

**Prompt**: *Necesitamos la siguiente información del documento para realizar un resumen: (1) tipo de evento (jornada, congreso, etc), (2) nombre del evento, (3) fecha y lugar donde se realizará el evento, (4) coordinación y (5) financiación, (6) ponentes incluyendo el nombre y el cargo*

*Resultado*: Información reorganizada según nuestra estructura solicitada.

---

### Generación de resumen

Queremos **realizar un resumen del evento** que incorporaremos en la propia página web.

**Prompt**: *Por favor, realiza un resumen de un párrafo del evento, indicando los temas de los que trata, a modo de resumen de la página. El resumen lo incorporaremos al final del documento anterior*

---

### Conversión a formato HTML

Vamos a **convertir toda la información anterior en HTML** para poder insertarla en nuestra página del sitio web de la Universidad.

**Prompt**: *Ahora, utilizando la información anterior que me has generado crea un documento HTML en formato evento. Necesito que sea una página elegante, con distinción clara de cada parte del evento (incluye la información estructurada del evento y el resumen del mismo que has elaborado anteriormente, añade datos estructurados para mejorar las búsquedas de Google en formato JSON-LD). El evento se celebra en Sevilla, en la Universidad Pablo de Olavide*

---

### Datos estructurados para SEO

La información estructurada permite a Google conocer más datos del evento al añadir metadatos. 

Puedes consultar más información en [https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data?hl=es-419](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data?hl=es-419)

---

### Resultado
Para verificar el resultado, utilizaremos [el visor HTML de Code Beautify](https://codebeautify.org/htmlviewer)

---

### Mejora de la página con elementos visuales

Vamos a mejorar la página añadiendo la imagen del evento y otras funcionalidades.

**Prompt**: *Por favor, añade al principio de la página web la imagen del evento, que se encuentra en https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png. Además me gustaría incluir a la derecha del lugar y la hora un icono para que puedan añadir el evento en Google Calendar*

---

### Enriquecimiento con información de los ponentes

Vamos a utilizar la **herramienta de búsqueda** para buscar información adicional.

**Prompt**: *Por favor, busca la información de los ponentes para añadir a la página web. Utiliza solo datos profesionales, importantes para añadir contexto al evento, descarta datos personales. Si encuentras alguna imagen de los ponentes añádela*

---

### Incorporación de la información a la página

Revisamos la información y le pedimos que la transforme a HTML para incorporarla en la página web. **En este caso no la vamos a incorporar al no ser relevante**

**Prompt**: *Convierte esta información en HTML e incorpórala en el contenido anterior de la página HTML en un apartado final llamado "Ponentes"*

---

### Resultado final

El resultado de la página web se puede ver aquí: [https://fgtortosa.github.io/uso-ia-generativa-ptgas-upo/](https://fgtortosa.github.io/uso-ia-generativa-ptgas-upo/)

---

## Conclusiones

- La IA generativa es una **herramienta versátil** para tareas como resumir, transformar y crear contenido (ej. páginas web desde carteles).
- Es crucial **guiar a la IA** con prompts claros y detallados, refinando los resultados paso a paso.
- Los modelos actuales (Claude, ChatGPT, Mistral, Gemini) ofrecen distintas fortalezas (razonamiento, multimodalidad, contexto amplio).
- La **supervisión humana** es esencial para verificar la precisión y adecuar el resultado final.
- **Precaución con datos sensibles:** Evitar información personal o confidencial al usar herramientas en la nube.

---
## Preguntas

