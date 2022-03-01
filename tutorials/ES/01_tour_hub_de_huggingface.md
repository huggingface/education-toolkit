# Un recorrido por el Hub de Hugging Face

<aside>
💡 ¡Hola!

Hemos reunido un conjunto de herramientas que l@s instructor@s universitari@s pueden usar para preparar fácilmente laboratorios, tareas o clases. El contenido está diseñado de manera autónoma, de modo que se puede incorporar fácilmente al plan de estudios existente. Este contenido es gratuito y utiliza tecnologías Open Source ampliamente conocidas (`transformers`, `gradio`, etc).

Alternativamente, puede solicitar que alguien del equipo de Hugging Face ejecute los tutoriales para su clase a través de la iniciativa [Gira de demo.cratización del ML](https://huggingface2.notion.site/huggingface2/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652)!

</aside>

**Duración:** 20 a 40 minutos

**Objetivo**: aprender a usar de manera eficiente el [Hub](http://huggingface.co) gratuito para poder colaborar en el ecosistema y dentro de equipos en proyectos de Machine Learning (ML).

**Metas de aprendizaje:**

- Conocer y explorar los más de 30,000 modelos compartidos en el Hub.
- Aprender formas eficientes de encontrar modelos y datasets adecuados para su aplicación.
- Aprender a trabajar de forma colaborativa.
- Explorar demos de ML creados por la comunidad.

**Formato:** Laboratorio corto o para llevar a casa

**Público:** Estudiantes de diferentes niveles con interés en usar modelos existentes o compartir los suyos.

**Requisitos previos**

- Comprensión de Machine Learning.
- (Opcional, pero recomendado) Experiencia con Git ([recurso](https://learngitbranching.js.org/)).

## ¿Por qué el Hub?

El Hub es una plataforma central donde cualquiera puede compartir y explorar modelos, datasets y demos de ML. El problema de "resolver la IA" no lo resolverá una sola empresa, sino una cultura de intercambio de conocimientos y recursos. Debido a esto, el Hub tiene como objetivo crear la colección más extensa de modelos, datasets y demos de código abierto.

Aquí hay algunos datos sobre el Hub de Hugging Face:

- Hay más de 30,000 modelos públicos.
- ¡Hay modelos para el procesamiento del lenguaje natural, la visión artificial, el audio/habla y el aprendizaje por refuerzo!
- Hay modelos para más de 180 idiomas. El Español es uno de los lenguajes más presentes.
- Cualquier biblioteca de ML puede aprovechar el Hub: desde TensorFlow y PyTorch hasta integraciones avanzadas con spaCy, SpeechBrain, Keras y otras 20 bibliotecas.

### Explorando un modelo

Empecemos la exploración de modelos. Puede acceder a 30,000 modelos (y creciendo) en [hf.co/models](http://hf.co/models). Verá a [gpt2](https://huggingface.co/gpt2) como uno de los modelos con más descargas. Hagamos clic en él.

Cuando haga clic en un modelo, el sitio web lo llevará a la tarjeta del modelo (model card en inglés). Una tarjeta del modelo es una herramienta que documenta modelos, proporciona información útil sobre estos y es esencial para la detección y reproducibilidad.

[https://www.youtube.com/embed/XvSGPZFEjDY](https://www.youtube.com/embed/XvSGPZFEjDY)

La interfaz tiene muchos componentes así que vamos a repasarlos:

- En la parte superior puede encontrar diferentes **etiquetas** para cosas como la tarea (_generación de texto, clasificación de imágenes, etc._), frameworks (_PyTorch, TensorFlow, etc._), el idioma del modelo (_inglés, árabe, etc._) y licencia (_por ejemplo, MIT_).

![](../../images/mode_card_tags.png)

- En la columna de la derecha, puede jugar con el modelo directamente en el navegador utilizando el API de Inferencia. GPT2 es un modelo de generación de texto, por lo que generará texto adicional dada una entrada inicial. Intente escribir algo como "It was a bright and sunny day". Este modelo está en inglés pero también puede probar con los existentes en español.

![](../../images/model_card_inference_api.png)

- En el medio, puede revisar el contenido de la tarjeta modelo. Tiene secciones como usos previstos y limitaciones, procedimiento de entrenamiento e Información de citas.

![](../../images/model_card_content.png)

¿De dónde vienen todos estos datos? En Hugging Face todo se basa en **repositorios de Git** y es de código abierto. Puede hacer clic en la pestaña "Files and Versions" que le permitirá ver todos los archivos del repositorio incluidos los pesos del modelo.

La tarjeta modelo es un archivo Markdown ([README.md](http://readme.md/)) que, además del contenido, contiene metadatos como las etiquetas.

![](../../images/model_card_git.png)

Dado que todos los modelos son repositorios basados en Git, obtiene el control de versiones listo para usar. Al igual que con GitHub, puede aplicar funciones de Git como cloning, adding, committing, branching y pushing. Si nunca ha usado Git antes, le sugerimos el siguiente [recurso](https://learngitbranching.js.org/).

**Reto 1**. Abra el archivo `config.json` del repositorio GPT2. El archivo de configuración contiene hiperparámetros, así como información útil para cargar el modelo. De este archivo, responda:

- ¿Cuál es la función de activación?
- ¿Cuál es el tamaño del vocabulario?

### **Explorando modelos**

Hasta ahora, hemos explorado un solo modelo. ¡Vamos por más! A la izquierda de [https://huggingface.co/models](https://huggingface.co/models), puede filtrar por diferentes cosas:

- **Tasks:** Hay soporte para docenas de tareas en diferentes dominios: visión artificial, procesamiento de lenguaje natural, audio y más. Puede hacer clic en +13 para ver todas las tareas disponibles.
  - **Bibliotecas** Aunque el Hub fue originalmente para modelos de transformers, el Hub tiene integración con docenas de bibliotecas. Puede encontrar modelos de Keras, spaCy, allenNLP y más.
- **Datasets:** El Hub también alberga miles de datasets, sobre los que encontrará más información más adelante.

![](../../images/model_card_filters.png)

- **Languages**: Muchos de los modelos del Hub están relacionados con el Procesamiento del Lenguaje Natural (PLN). Puede encontrar modelos para cientos de idiomas, incluidos idiomas de bajos recursos.

**Reto 2**. ¿Cuántos modelos de clasificación de tokens hay en inglés?

**Reto 3**. Si tuviera que elegir un modelo en español de Reconocimiento Automático de Voz, ¿cuál elegiría? (Puede ser cualquier modelo para esta tarea e idioma).

### **Agregar un modelo**

Supongamos que desea subir un modelo al Hub. Este modelo podría ser un modelo de cualquier biblioteca de ML: Scikit-learn, Keras, Transformers, etc.

Vayamos a través de los pasos:

1. Vaya a [huggingface.co/new](http://huggingface.co/new) para crear un nuevo repositorio de modelos. Los repositorios que haga pueden ser públicos o privados.
2. Comience con un repositorio público que tiene una tarjeta modelo. Puede subir su modelo mediante la interfaz de usuario web o hacerlo con Git. Si nunca ha usado Git antes le sugerimos que solo use la interfaz web. Puede hacer clic en "Add file" y arrastrar y soltar los archivos que desea agregar. Si desea comprender el flujo de trabajo completo, sigamos con el enfoque de Git.

   1. Instale git y git-lfs en su sistema.
      1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
      2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Los archivos grandes deben subirse con Git LFS. Git no funciona bien una vez que los archivos tienen más de unos pocos megabytes lo cual es frecuente en ML. ¡Los modelos ML pueden tener hasta gigabytes o terabytes! 🤯

   b. Clone el repositorio que acaba de crear

```python
git clone https://huggingface.co/<your-username>/<your-model-id>
```

c. Vaya al directorio e inicialice Git LFS

1. Opcional. Ya proporcionamos una lista de extensiones de archivo comunes para los archivos grandes en `.gitattributes`. Si los archivos que desea subir no están incluidos en el archivo `.gitattributes`, es posible que necesite lo que se muestra aquí: Puede hacerlo con

```python
git lfs track "*.your_extension"
```

```python
git lfs install
```

d. Agregue sus archivos al repositorio. Los archivos dependen del framework/bibliotecas que esté utilizando. En general, lo importante es que proporcione todos los artefactos necesarios para cargar el modelo. Por ejemplo:

1. Para TensorFlow, es posible que desee subir un `SavedModel` o archivo `h5`.
2. Para PyTorch, por lo general, es un `pytorch_model.bin`.
3. Para Scikit-Learn, generalmente es un archivo `joblib`

Aquí hay un ejemplo en Python guardando un archivo de modelo de Scikit-Learn.

```python
from sklearn import linear_model
reg = linear_model.LinearRegression()
reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

from joblib import dump, load
dump(reg, 'model.joblib')
```

e. Haga commit y push a sus archivos (asegúrese de que el archivo guardado esté dentro del repositorio).

```python
git add .
git commit -m "First model version"
git push
```

¡Y hemos terminado! ¡Puede consultar su repositorio con todos los archivos agregados!

![](../../images/model_card_updated_repo.png)

La interfaz de usuario le permite explorar los archivos del modelo y los commits. Puede ver la diferencia introducida por cada commit.

**Reto 4**. ¡Su turno! Suba un modelo ficticio de la biblioteca de su elección.

Ahora que el modelo está en el Hub, ¡otros pueden encontrarlo! También puede colaborar con otros fácilmente creando una organización. El alojamiento a través del Hub permite que un equipo actualice los repositorios y haga cosas a las que podría estar acostumbrado, como trabajar en branches y en colaboración. El Hub también permite la creación de versiones en sus modelos: si un punto de control (checkpoint) del modelo se rompe, siempre puede volver a una versión anterior.

En la parte superior de `README` puede encontrar algunos metadatos. Ahora mismo solo encontrará la licencia pero puede añadir más cosas. Probemos algo de esto:

```yaml
 tags:
- es       # Esto se detectará automáticamente como una etiqueta de idioma.
- bert     # Puede tener etiquetas adicionales para filtrar.
- text-classification # Se detectará automáticamente como una etiqueta de tarea.
datasets:
- llamas # Esto se vinculará a un dataset en el Hub, si existe.
```

**Reto 5**. Utilizando la [documentación](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined) cambie el ejemplo predeterminado en el widget.

Los metadatos permiten que las personas descubran su modelo rápidamente. Su modelo ahora aparecerá cuando busque modelos de clasificación de texto en español. El modelo también aparecerá al mirar el dataset.

Espera... ¿datasets?

### Datasets

En los procesos de creación de ML, generalmente se tiene un dataset para entrenar el modelo. El Hub aloja alrededor de 3,000 datasets que son Open Source y de uso gratuito en múltiples dominios. Además, la [biblioteca](https://huggingface.co/docs/datasets/) de`datasets` de código abierto permite el uso fácil de estos datasets, incluidos los datasets enormes, utilizando funciones muy convenientes como el streaming. Este laboratorio no pasará por la biblioteca, pero explica cómo explorarlos.

Al igual que con los modelos, puede dirigirse a [https://hf.co/datasets](https://hf.co/datasets). A la izquierda, puede encontrar diferentes filtros según el task, la licencia y el tamaño del datasets.

Exploremos el dataset [GLUE](https://huggingface.co/datasets/glue); un dataset famoso que se utiliza para probar el rendimiento de los modelos de PLN.

- De manera similar a los repositorios de modelos, tiene una tarjeta de datasets que documenta el dataset. Si se desplaza un poco hacia abajo, encontrará cosas como el resumen, la estructura y más.

![](../../images/datasets_card.png)

- En la parte superior puede explorar una porción del Su modelo ahora aparecerá cuando busque modelos de clasificación de texto en español. El modelo también aparecerá al mirar el dataset. directamente en el navegador. El dataset de GLUE se divide en varios subdatasets que puede seleccionar, como COLA y QNLI.

  ![](../../images/datasets_slices.png)

- A la derecha de la tarjeta del dataset puede ver una lista de modelos entrenados con este dataset.

![](../../images/datasets_models_trained.png)

**Reto 6**. Busque el dataset de Common Voice. Responda estas preguntas:

- ¿Para qué tareas se puede usar el dataset de Common Voice?
- ¿Cuántos idiomas están cubiertos en este dataset?
- ¿Cuáles son las particiones del dataset (ejemplo, train)?

### Demos de ML

Compartir sus modelos y datasets es genial, pero crear un demo interactivo disponible públicamente es aún más genial. Los demos de modelos son una parte cada vez más importante del ecosistema. Los demos permiten:

- que las personas que desarrollan modelos puedan **presentar** fácilmente su trabajo a una amplia audiencia, como en presentaciones de stakeholders, conferencias y proyectos de cursos;
- aumentar la **reproducibilidad** en Machine Learning al reducir la barrera para probar un modelo;
- compartir con una audiencia no técnica **el impacto de un modelo;**
- crear un **portafolio** de Machine Learning.

Existen frameworks de Python de código abierto como Gradio y Streamlit que permiten construir estos demos muy fácilmente, y herramientas como Hugging Face [Spaces](http://hf.co/spaces/launch) que permiten alojarlos y compartirlos. Como laboratorio de seguimiento recomendamos realizar el tutorial **2️⃣ Cree y aloje demos de Machine Learning con Gradio y Hugging Face**.

> En ese tutorial aprenderá a:
>
> - Explorar demos de ML creados por la comunidad.
> - Crear un demo rápido para su modelo de Machine Learning en Python usando la biblioteca `gradio`.
> - Alojar los demos de forma gratuita con Hugging Face Spaces.
> - Agregar su demo a su organización en Hugging Face para su clase o conferencia.
>
> **_Duración: 20-40 minutos_**
>
> 👉 [Clic aquí para acceder al tutorial](https://colab.research.google.com/drive/1K5tP5NBWwtezBg3Kp4wpD5KI6JZ6oCg9)
