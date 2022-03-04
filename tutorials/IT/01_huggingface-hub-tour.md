# Workshop: Un tour attraverso l'hub di Hugging Face

<aside>

💡 **Benvenute e benvenuti!**

Abbiamo raccolto un set di strumenti che possono essere usati dagli insegnanti universitari per preparare laboratori o lezioni. Il materiale è auto-contenuto in modo tale che possa essere facilmente inserito in un programma esistente. Il contenuto è **gratuito** e usa tecnologie open-source molto note (`transformers`, `gradio`, etc).

In alternativa, puoi fare richiesta affinche qualcuno del team di Hugging Face svolga i tutorial all'interno del tuo corso tramite le iniziative di [ML Demo-cratization Tour](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652)

Puoi trovare tutti i tutorial e le risorse che abbiamo accolto [qui](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599).

</aside>

**Durata:** da 20 a 40 minuti

**Obiettivo:** Impara come utilizzare in modo efficiente la [piattaforma Hub](https://huggingface.co/) gratuita (http://hf.co) per di collaborare nell'ecosistema e all'interno dei team in progetti di Machine Learning (ML).

Obiettivi di apprendimento:

- Conoscere ed esplorare gli oltre 30.000 modelli condivisi su Hub.
- Apprendere modi efficienti per trovare modelli e set di dati adatti al tuo task.
- Apprendere come contribuire e lavorare in modo collaborativo.
- Esplorare le demo delle tecniche di Apprendimento Automatico (Machine Learning) create dalla comunità.

**Formato:** Laboratorio breve o da casa

**Pubblico:** Studenti con qualsiasi conoscenza pregressa interessati ad utilizzare modelli esistenti o a condividere i propri.

**Prerequisiti**

- Comprensione di alto livello del Machine Learning.
- (Opzionale, ma suggerito) Esperienza con Git ([risorsa](https://learngitbranching.js.org/))

## **Perché l'Hub?**

L'Hub è una piattaforma centralizzata dove chiunque può condividere ed esplorare modelli, collezioni di dati e demo di ML. Il problema di "risolvere l'AI" non sarà risolto da una singola azienda, ma da una cultura di condivisione delle conoscenze e delle risorse. Per questo motivo, l'Hub mira a costruire la più ampia collezione di modelli Open Source, set di dati e demo.


Ecco alcune informazioni su Hugging Face Hub:

- Ci sono oltre 30.000 modelli pubblici.
- Ci sono modelli per il Natural Language Processing, Computer Vision, Audio/Parolat, e Reinforcement Learning!
- Ci sono modelli per oltre 180 lingue.
- Qualsiasi libreria di ML può sfruttare l'Hub: da TensorFlow e PyTorch a integrazioni avanzate con spaCy, SpeechBrain e altre 20 librerie.

## Esplorare un modello

Diamo il via all'esplorazione dei modelli. Puoi accedere a 30.000 modelli su [hf.co/models](http://hf.co/models). Vedrete [gpt2](https://huggingface.co/gpt2), uno dei modelli con più download. Clicchiamo su di esso.

Il sito vi porterà alla scheda del modello quando cliccate su di esso. Una scheda del modello è uno strumento che ne contiene la documentazion, fornendo informazioni utili sui modelli ed è essenziale per aumentarne la visibilità e la riproducibilità.

L'interfaccia è composta da più parti, esaminiamole:

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- In cima, puoi trovare diversi **tags** per cose come il compito svolto (*generazione di testo, classificazione di immagini*, ecc.), i frameworks utilizzati per la sua implementazione (*PyTorch*, *TensorFlow*, ecc.), la lingua del modello (*Inglese*, *Arabo*, *ecc.*), e la licenza (*es. MIT*).

![](../../images/mode_card_tags.png)

- Nella colonna di destra, puoi fare dei test con il modello direttamente nel browser usando l'*Inference API*. GPT2 è un modello di generazione di testo, quindi genererà un testo aggiuntivo dato un input iniziale. Provate a digitare qualcosa come "Era una giornata luminosa e soleggiata".

![](../../images/model_card_inference_api.png)

- Al centro, si può passare attraverso il contenuto della scheda del modello. Contiene sezioni che ne descrivono gli usi previsti e limitazioni, la procedura usata per l'addestramento e informazioni per le citazioni.

![](../../images/model_card_content.png)

Da dove vengono tutti questi dati? A Hugging Face, tutto è basato su **repository Git** ed è liberamente accessibile (open-source). Puoi cliccare sulla scheda "Files and Versions", che ti permetterà di vedere tutti i file del repository, inclusi i pesi del modello. La scheda del modello è un file markdown **([README.md](http://README.md))** che oltre al contenuto contiene metadati come i tag.

![](../../images/model_card_git.png)

Poiché tutti i modelli sono contenuti in delle repository basate su Git, esse saranno automaticamente sottoposte al controllo delle versioni. Proprio come con GitHub, puoi fare cose come clonare `git clone`, aggiungere `git add`, committare `git commit`, ramificare `git fork` e pushare `git push`. Se non hai mai usato Git prima, ti suggeriamo di dare un'occhiata [qui](https://learngitbranching.js.org/).


**Sfida 1**. Apri il file `config.json` del repository GPT2. Il file di configurazione contiene gli iperparametri e altre informazioni utili per caricare il modello. Utilizzando le informazioni contenute in questo file, rispondi alle domande seguenti:

- Qual è la funzione di attivazione?
- Qual è la dimensione del vocabolario?


## **Exploring Models**

So far, we’ve explored a single model. Let’s go wild! At the left of [https://huggingface.co/models](https://huggingface.co/models), you can filter for different things:

- **Tasks:** There is support for dozens of tasks in different domains: Computer Vision, Natural Language Processing, Audio, and more. You can click the +13 to see all available tasks.
  - **Libraries:** Although the Hub was originally for transformers models, the Hub has integration with dozens of libraries. You can find models of Keras, spaCy, allenNLP, and more.
- **Datasets:** The Hub also hosts thousands of datasets, as you’ll find more about later.

![](../../images/model_card_filters.png)

- **Languages:** Many of the models on the Hub are NLP-related. You can find models for hundreds of languages, including low-resource languages.

**Challenge 2**. How many token classification models are there in English?

**Challenge 3**. If you had to pick a Spanish model for Automatic Speech Recognition, which would you choose? (It can be any model for this task and language)

## Adding a model

Let’s say you want to upload a model to the Hub. This model could be a model of any ML library: Scikit-learn, Keras, Transformers, etc.

Let’s go through the steps:

1. Go to [huggingface.co/new](http://huggingface.co/new) to create a new model repository. The repositories you make can be either public or private.
2. You start with a public repo that has a model card. You can upload your model either by using the Web UI or by doing it with Git. If you’ve never used Git before, we suggest just using the Web interface. You can click Add File and drag and drop the files you want to add. If you want to understand the complete workflow, let’s go with the Git approach.

    1. Install both git and git-lfs installed on your system.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Large files need to be uploaded with Git LFS.  Git does not work well once your files are above a few megabytes, which is frequent in ML. ML models can be up to gigabytes or terabytes! 🤯
    2. Clone the repository you just created

        ```python
        git clone https://huggingface.co/<your-username>/<your-model-id>
        ```

    3. Go to the directory and initialize Git LFS
        1. Optional. We already provide a list of common file extensions for the large files in `.gitattributes`, If the files you want to upload are not included in the `.gitattributes` file, you might need as shown here: You can do so with

            ```python
            git lfs track "*.your_extension"
            ```

            ```python
             git lfs install
            ```

    4. Add your files to the repository. The files depend on the framework/libraries you’re using. Overall, what is important is that you provide all artifacts required to load the model. For example:
        1. For TensorFlow, you might want to upload a SavedModel or `h5` file.
        2. For PyTorch, usually, it’s a `pytorch_model.bin`.
        3. For Scikit-Learn, it’s usually a `joblib` file.

        Here is an example in Python saving a Scikit-Learn model file.

        ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. Commit and push your files (make sure the saved file is within the repository)

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

And we're done! You can check your repository with all the recently added files!

![](../../images/model_card_updated_repo.png)

The UI allows you to explore the model files and commits and to see the diff introduced by each commit.

**Challenge 4**. It’s your turn! Upload a dummy model of the library of your choice.

Now that the model is in the Hub, others can find them! You can also collaborate with others easily by creating an organization. Hosting through the Hub allows a team to update repositories and do things you might be used to, such as working in branches and working collaboratively. The Hub also enables versioning in your models: if a model checkpoint is suddenly broken, you can always head back to a previous version.

At the top of the `README`, you can find some metadata. You will only find the license right now, but you can add more things. Let’s try some of it:

```yaml
 tags:
- es       # This will automatically be detected as a language tag.
- bert     # You can have additional tags for filtering
- text-classification # This will automatically be detected as a task tag.
datasets:
- llamas # This will link to a dataset on the Hub if it exists.
```

**Challenge 5**. Using the [documentation](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined), change the default example in the widget.

The metadata allows people to discover your model quickly. Your model will now show up when you search for text classification models in Spanish. The model will also show up when looking at the dataset.

Wait...datasets?

## Datasets

With ML pipelines, you usually have a dataset to train the model. The Hub hosts around 3000 datasets that are open-sourced and free to use in multiple domains. On top of it, the open-source `datasets` [library](https://huggingface.co/docs/datasets/) allows the easy use of these datasets, including huge ones, using very convenient features such as streaming. This lab won't go through the library, but it does explain how to explore them.

Similar to models, you can head to [https://hf.co/datasets](https://hf.co/datasets). At the left, you can find different filters based on the task, license, and size of the dataset.

Let’s explore the [GLUE](https://huggingface.co/datasets/glue) dataset, which is a famous dataset used to test the performance of NLP models.

- Similar to model repositories, you have a dataset card that documents the dataset. If you scroll down a bit, you will find things such as the summary, the structure, and more.

![](../../images/datasets_card.png)

- At the top, you can explore a slice of the dataset directly in the browser. The GLUE dataset is divided into multiple sub-datasets (or subsets) that you can select, such as COLA and QNLI.

  ![](../../images/datasets_slices.png)

- At the right of the dataset card, you can see a list of models trained on this dataset.

![](../../images/datasets_models_trained.png)

**Challenge 6**. Search for the Common Voice dataset. Answer these questions:

- What tasks can the Common Voice dataset be used to?
- How many languages are covered in this dataset?
- Which are the dataset splits?

## ML Demos

Sharing your models and datasets is great, but creating an interactive, publicly available demo is even cooler. Demos of models are an increasingly important part of the ecosystem. Demos allow:

- model developers to easily **present** their work to a wide audience, such as in stakeholder presentations, conferences, and course projects
- to increase **reproducibility** in machine learning by lowering the barrier to test a model
- to share with a non-technical audience **the impact of a model**
- build a machine learning **portfolio**

There are Open-Source Python frameworks such as Gradio and Streamlit that allow building these demos very easily, and tools such as Hugging Face [Spaces](http://hf.co/spaces/launch) which allow to host and share them. As a follow-up lab, we recommend doing the **Build and Host Machine Learning Demos with Gradio & Hugging Face** tutorial.

> In this tutorial, you get to:
>
> - Explore ML demos created by the community.
> - Build a quick demo for your machine learning model in Python using the `gradio` library
> - Host the demos for free with Hugging Face Spaces
> - Add your demo to the Hugging Face org for your class or conference
>
> ***Duration: 20-40 minutes***
>
> 👉 [click here to access the tutorial](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/tutorials/EN/02_ml-demos-with-gradio.ipynb)
