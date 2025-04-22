---
title: Uso de la inteligencia artificial generativa para el PTGAS de la Universidad Pablo de Olavide, de Sevilla  - Generar contenido
author: Paco García Tortosa. Servicio de Informática - Universidad de Alicante
date: 2025-4-21
marp: true
tags:
  - CharlaIA
---

## Consideraciones iniciales
- La IA generativa puede ser una ayuda para las tareas del día a día del colectivo PTGAS de la Universidad de Pablo de Olavide
- Es una herramienta de apoyo, **necesita ser supervisada**
- Como se usa en la nube hay que evitar el uso de datos personales o de información sensible
- Es buena en tareas lingüísticas, no en razonamiento ni matemáticas (esto esta cambiando rápidamente)

---

## Conceptos
**Prompt**:  Texto con el que inicia la conversación. 

---

## Conceptos

**Prompt**

1. Hay que detallar el tipo de salida que se desee y toda aquella información que sea relevante (contexto). 
2. Si la salida que se desea es compleja comenzar con una aproximación al problema para a continuación ir añadiendo la complejidad. 
3. En algunos casos puede ser interesante utilizar modelos con capacidad de razonamiento, por su capacidad de estructurar la tarea. **Para estos modelos, es útil dar instrucciones paso a paso o pedirles que "piensen en voz alta" (Chain-of-Thought).**

---

## Conceptos

**Contexto**

La información inicial y la recibida durante la conversación. Normalmente el contexto es temporal, la herramienta lo almacena durante algún tiempo y luego lo pierde

---

## Conceptos

**Multimodalidad**

El modelo permite el uso de texto, imágenes, audio, etc. No funciona igual de bien con todos los tipos de datos, normalmente con texto y con imágenes si se quiere obtener información de ellas (como OCR)

---

## Conceptos

**Razonamiento**

Algunos modelos pueden descomponer tareas complejas en pasos lógicos, planificar y seguir una estrategia. Esto es útil para problemas que requieren análisis detallado o seguir instrucciones precisas.

---

## Modelos que podemos usar
1. claude
2. chatgpt
3. mistral
4. gemini
5. bing (copilot)

---

### Claude.ai
- Modelo de Anthropic
- En es el mejor modelo para tareas de programación, incluyendo por supuesto las formulas de excel. Posee **buenas capacidades de razonamiento.**
- Hay que registrarse para usarlo, en [https://claude.ai](https://claude.ai)

---

### Chatgpt.com
- Modelo de OpenAI
- Es un buen modelo para tareas de razonamiento, **especialmente en su versión de pago (GPT-4).**
- Hay que registrarse en [https://chatgpt.com](https://chatgpt.com)

---

### Mistral.ai
- Modelo de Mistral (único modelo europeo)
- Funciona bastante bien en multimodalidad. Buena capacidad para realizar traducciones entre idiomas europeos
- Hay que registrarse en [https://chat.mistral.ai/](https://chat.mistral.ai/)
)

---

### Google Gemini
- Genera texto e imágenes
- Se puede usar sin registrarse desde una cuenta de *gmail*. Para acceder: [https://gemini.google.com/](https://gemini.google.com/)
- Ha mejorado mucho últimamente, recomendado para tareas que necesiten un contexto muy grande (grandes documentos)

---
## Ejemplo práctico

Creación de una página web con la noticia de un evento que va a tener lugar en la Universidad

---

1. La información que nos proporcionan está en un cartel del propio evento
2. Vamos a utilizar distintos modelos, los mas conocidos, pero con un mismo prompt y vamos a afinar la salida
3. Todos los modelos nos van a obligar a registrarnos
4. Cada modelo puede dar una respuesta distinta
5. Cada vez que se le pregunta al modelo también puede dar una respuesta distinta (*esta inteligencia artificial es generativa*)

----

1. Registrarnos o loguearnos en mistral: [https://chat.mistral.ai/](https://chat.mistral.ai/)
2. Descargar el documento de: [https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png](https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png)
3. Subir la imagen a la herramienta, utilizando el icono del clip que hay en la parte izquierda

---

Acercamiento inicial al problema, estamos usando el modelo sin indicaciones

Prompt: *Transcribe el contenido del documento*

---

El resultado corresponde a la transcripción de los textos que contiene el cartel en el mismo orden en que aparece en la imagen:
- Nombre de la jornada
- Fecha de la charla
- Descripción de los ponentes
- Lugar y hora del evento
- Coordinación
- Financiación

---


Queremos **transformar la información** para que tenga un orden adecuado al uso que queremos darle. Utilizamos las indicaciones para ello

Prompt: *Necesitamos la siguiente información del documento para realizar un resumen: (1) tipo de evento (jornada, congreso, etc), (2) nombre del evento, (3) fecha y lugar donde se realizará el evento, (4) coordinación y (5) financiación, (6) ponentes incluyendo el nombre y el cargo*

Como vemos ha transformado la información, dandole sentido en base a la indicación que le hemos dado

---

Queremos **realizar un resumen del evento** que incorporaremos en la propia página web

Prompt: *Por favor, realiza un resumen de un párrafo del evento, indicando los temas de los que trata, a modo de resumen de la página*. El resumen lo incorporaremos al final del documento anterior

---

Vamos a **convertir toda la información anterior en html** para poder insertarla en nuestra página del sitio web de la Universidad.

Prompt: *Ahora, utilizando la información anterior que me has generado crea un documento html en formato evento. Necesito que sea una página elegante, con distinción clara de cada parte del evento (incluye la información estructurada del evento y el resumen del mismo que has elaborado anteriormente, añade datos estructurados para mejorar las búsquedas de google en formato JSON-LD). El evento se celebra en Sevilla, en la universidad Pablo de Olavide*

La información estructurada le permite a Google conocer mas datos del evento al añadir otros datos. Podeis consultar mas información en [https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data?hl=es-419](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data?hl=es-419)

Vamos a comprobar como ha quedado la página visionandola con un visor externo. Para ello vamos a utilizar [el visor HTML de Code Beautify](https://codebeautify.org/htmlviewer)

Como queremos mejorar la página vamos a pedirle que en la cabecera añada la imagen utilizada para crear la pagina web. La página del evento se encuentra en [https://eventos.upo.es/133339/detail/iv-jornada-de-traduccion-e-interpretacion-en-las-fuerzas-y-cuerpos-de-seguridad-del-estado.html](https://eventos.upo.es/133339/detail/iv-jornada-de-traduccion-e-interpretacion-en-las-fuerzas-y-cuerpos-de-seguridad-del-estado.html). Para ello copiamos la direccion de la imagen

Prompt: *Por favor, añade al principio de la pagina web la imagen del evento, que se encuentra en https://eventos.upo.es/_files/_event/_133339/_header_img/_195709.png. Además me gustaría incluir a la derecha del lugar y la hora un icono para que puedan añadir el evento en google calendar*

---

Vamos a utilizar la **herramienta de búsqueda** para buscar información de los ponentes

Prompt: *Por favor, busca la información de los ponentes para añadir a la pagina web. Utiliza solo datos profesionales, importantes para añadir contexto al evento, descarta datos personales. Si encuentras alguna imagen de los ponentes añadela*

----

Revisamos la información y le pedimos que la transforme a html *para incorporarla en la página web*

Prompt: *Convierte esta información en html e incorporala en el contenido anterior de la pagina html en un apartado final llamado ponentes*

Ajustamos la salida a nuestras necesidades:

Prompt: *Quita la imagen del ponente y separa el contenido del resumen de de los ponentes claramente, para ello omite el resaltado azul y el fondo gris en los ponentes, manteniendo el código html normal.*


Verificamos la respuesta y la subimos a nuestro gestor de contenidos

-----

El resultado de la pagina web se puede ver aquí: [https://fgtortosa.github.io/uso-ia-generativa-ptgas-upo/](https://fgtortosa.github.io/uso-ia-generativa-ptgas-upo/)

-----

## Ejemplo práctico 

Creación de una imagen a partir de indicaciones

---

Microsoft Bing: https://www.bing.com/images/create 

1. Registrarnos o loguearnos en Microsoft Bing: [https://www.bing.com/images/create]([https://www.bing.com/images/create])
2. Necesitamos un usuario de microsoft

---

#### Pregunta (prompt)

Necesito una imagen para una página web. Esta imagen debe de ser de una ciudad mediterránea, con una avenida con palmeras, el mar al lado y la parte trasera una pequeña montaña. La imagen por favor en blanco y negro y la ciudad de los años 60 del siglo pasado

----

#### Pregunta (prompt)

Afino: Necesito una imagen que debe corresponder a una ciudad mediterránea, con una avenida con palmeras, el mar al lado y la parte trasera una pequeña montaña. La imagen por favor en blanco y negro y la ciudad de los años 60 del siglo pasado. La ciudad a la izquierda con los edificios monumentales, a la derecha la playa y al fondo a la izquierda, también junto a la playa, la pequeña montaña con una fortificación de tipo castillo (mediterráneo). La imagen en formato fotográfico, del tipo polaroit, con los bordes un poco blanquecinos por el paso del tipo, de tipo postal. En formato alargado para usar en una web

---

![Ciudad mediterránea](imagen-bing.jpg)
