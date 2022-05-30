# Atelier : Une visite du *Hub* d'Hugging Face

<aside>

<aside>

👋 **Bienvenue !**

Nous avons assemblé une boite à outil que les professeurs du supérieur peuvent utiliser pour préparer des séances de travaux dirigés, des cours ou des devoirs. Le contenu est autonome, de manière à ce qu'il puisse être intégrer dans un cours pré-existant. Le contenu est gratuit et utilise des technologies Open Source connues (`transformers`, `gradio`, etc).

Il est aussi possible de demander à un membre de l'équipe d'Hugging Face de présenter les tutoriels dans un de vos cours via l'initiative [*ML demo.cratization tour*](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652) !

Vous pouvez trouver tous les tutoriels et ressources que nous avons rassemblés [ici](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599) (en anglais).

</aside>

**Durée :** 20 à 40 minutes

**Objectif :** Apprendre à utiliser efficacement le [*Hub*](http://hf.co) pour pouvoir collaborer dans l'écosystème et au sein des équipes dans des projets d'apprentissage automatique.

Objectifs d'apprentissage :

- Apprendre à connaître et explorer les plus de 50 000 modèles partagés sur le *Hub*.
- Apprendre des méthodes efficaces pour trouver des modèles et des jeux de données adaptés à votre tâche.
- Apprendre à contribuer et à travailler en collaboration.
- Explorez les démos d'apprentissage automatique créées par la communauté.

**Format : ** TD courts ou pour des devoirs maisons.

**Public :** Étudiants de tous horizons intéressés par l'utilisation de modèles existants ou par le partage de leurs propres modèles.

**Prérequis**

- Compréhension de haut niveau de l'apprentissage automatique.
- (Facultatif, mais encouragé) Expérience avec Git ([ressource](https://learngitbranching.js.org/))

## **Pourquoi le *Hub* ?**

Le *Hub* est une plateforme centrale où chacun peut partager et explorer des modèles, des jeux de données et des démonstrations d'apprentissage automatique. Le problème de « résoudre l'IA » ne sera pas résolu par une seule entreprise mais par une culture de partage des connaissances et des ressources. Pour cette raison, le *Hub* vise à construire la plus vaste collection de modèles, de jeux de données et de démos disponibles en Open Source.

Voici quelques faits concernant le *Hub* d'Hugging Face :

- Il existe plus de 50 000 modèles publics.
- Il existe des modèles pour le traitement du langage naturel, la vision par ordinateur, l'audio/la parole et l'apprentissage par renforcement !
- Il existe des modèles pour plus de 180 langues.
- Toute bibliothèque d'apprentissage automatique peut exploiter le *Hub* : de TensorFlow et PyTorch aux intégrations avancées avec spaCy, SpeechBrain et 20 autres bibliothèques.

## Exploration d'un modèle

Commençons par l'exploration des modèles. Vous pouvez accéder à 50 000 modèles sur [hf.co/models](http://hf.co/models). Vous verrez que [gpt2](https://huggingface.co/gpt2) est l'un des modèles les plus téléchargés. Cliquez dessus.

Lorsque vous cliquez sur un modèle, le site Web vous amène à la carte du modèle. Une carte de modèle est un outil qui documente et fournit des informations utiles sur un modèle et étant essentiel pour la découverte et la reproductibilité.

L'interface comporte de nombreux composants, passons-les en revue :

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- En haut, vous pouvez trouver différents **tags** pour des choses telles que la tâche (*génération de texte, classification d'images*, etc.), les *frameworks* (*PyTorch*, *TensorFlow*, etc.), la langue du modèle (*anglais*, *français*, *etc.*) et la licence (*e.g. MIT*).

![](./images/mode_card_tags.png)

- Dans la colonne de droite, vous pouvez jouer avec le modèle directement dans le navigateur à l'aide d'API d'*Inference*. Le GPT2 est un modèle de génération de texte, il va donc générer du texte supplémentaire à partir d'une entrée initiale. Essayez de taper quelque chose en anglais comme « It was a bright and sunny day » (c'était une journée claire et ensoleillée).

![](./images/model_card_inference_api.png)

- Au milieu, vous pouvez parcourir le contenu de la carte. Elle comporte des sections telles que Utilisations prévues et limites, Procédure d'entraînement et Informations sur la citation.

![](./images/model_card_content.png)

D'où viennent toutes ces données ? Chez Hugging Face, tout est basé sur des dépôts **Git** et est open-sourcé. Vous pouvez cliquer sur l'onglet *Files and Versions* (ficheirs et versions) qui vous permettra de voir tous les fichiers du dépôt, y compris les poids du modèle. La carte est un fichier markdown **([README.md](http://README.md))** qui, en plus du contenu, contient des métadonnées telles que les balises.

![](./images/model_card_git.png)

Comme tous les modèles sont des dépôts basés sur Git, vous bénéficiez d'un contrôle de version dès le départ. Tout comme avec GitHub, vous pouvez effectuer des opérations telles que le clonage, l'ajout, l'engagement, le branchement et la poussée de Git. Si vous n'avez jamais utilisé Git auparavant, nous vous suggérons la [ressource](https://learngitbranching.js.org/) suivante.

**Défi 1** : Ouvrez le fichier `config.json` du dépôt GPT2. Le fichier config contient des hyperparamètres ainsi que des informations utiles pour le chargement du modèle. A partir de ce fichier, répondez aux questions suivantes :

- Quelle est la fonction d'activation ?
- Quelle est la taille du vocabulaire ?

## **Exploration des modèles**

Jusqu'à présent, nous avons exploré un seul modèle. Soyons fous ! À gauche de [https://huggingface.co/models](https://huggingface.co/models), vous pouvez filtrer pour différentes choses :

- **Tasks (tâches) :** Il existe un support pour des dizaines de tâches dans différents domaines : Vision par ordinateur, traitement du langage naturel, audio, etc. Vous pouvez cliquer sur le +13 pour voir toutes les tâches disponibles.
  - **Librairies (bibliothèques) :** Bien que le *Hub* était à l'origine pour les modèles de transformateurs, le Hub a une intégration avec des dizaines de bibliothèques. Vous pouvez trouver des modèles de Keras, spaCy, allenNLP, et plus encore.
- **Datasets (jeux de données) :** Le *Hub* héberge également des milliers de jeux de données, comme vous le découvrirez plus tard.

![](./images/model_card_filters.png)

- **Languages (langues) :** La plupart des modèles du *Hub* sont liés au langage naturel. Vous pouvez trouver des modèles pour des centaines de langues, y compris des langues à faibles ressources.

**Défi 2** : Combien de modèles de classification de *tokens* existe-t-il en anglais ?

**Défi 3** : Si vous deviez choisir un modèle espagnol pour la reconnaissance automatique de la parole, lequel choisiriez-vous ? (Il peut s'agir de n'importe quel modèle pour cette tâche et cette langue)

## Ajout d'un modèle

Disons que vous voulez télécharger un modèle sur le *Hub*. Ce modèle peut être un modèle de n'importe quelle bibliothèque ML : Scikit-learn, Keras, Transformers, etc.

Passons en revue les étapes :

1. Allez sur [huggingface.co/new](http://huggingface.co/new) pour créer un nouveau dépôt de modèle. Les dépôts que vous créez peuvent être publics ou privés.
2. Vous commencez avec un dépôt public qui a une carte de modèle. Vous pouvez télécharger votre modèle soit en utilisant l'interface Web, soit en le faisant avec Git. Si vous n'avez jamais utilisé Git auparavant, nous vous suggérons d'utiliser l'interface Web. Vous pouvez cliquer sur « Add File » et glisser-déposer les fichiers que vous souhaitez ajouter. Si vous souhaitez comprendre le flux de travail complet, optons pour l'approche Git.

    1. Installez à la fois git et git-lfs sur votre système.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Les gros fichiers doivent être téléchargés avec Git LFS.  Git ne fonctionne pas bien dès que vos fichiers dépassent quelques mégaoctets, ce qui est fréquent en apprentissage automatique. Les modèles d'apprentissage automatique peuvent atteindre des gigaoctets ou des téraoctets ! 🤯
    2. Clonez le dépôt que vous venez de créer

        ```python
        git clone https://huggingface.co/<your-username>/<your-model-id>
        ```

    3. Allez dans le répertoire et initialisez Git LFS
        1. Facultatif. Nous fournissons déjà une liste d'extensions de fichiers courantes pour les gros fichiers dans `.gitattributes`, Si les fichiers que vous voulez télécharger ne sont pas inclus dans le fichier `.gitattributes`, vous pourriez avoir besoin comme indiqué ici : Vous pouvez le faire avec

            ```python
            git lfs track "*.your_extension"
            ```

            ```python
             git lfs install
            ```

    4. Ajoutez vos fichiers au dépôt. Les fichiers dépendent du *framework*/des bibliothèques que vous utilisez. Globalement, l'important est que vous fournissiez tous les artefacts nécessaires au chargement du modèle. Par exemple :
        1. Pour TensorFlow, vous pourriez vouloir charger un fichier SavedModel ou `h5`.
        2. Pour PyTorch, habituellement, c'est un `pytorch_model.bin`.
        3. Pour Scikit-Learn, il s'agit généralement d'un fichier `joblib`.

        Voici un exemple en Python de sauvegarde d'un fichier modèle Scikit-Learn.

        ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. Commitez et poussez vos fichiers (assurez-vous que le fichier sauvegardé se trouve dans le dépôt).

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

Et c'est terminé ! Vous pouvez vérifier votre dépôt avec tous les fichiers récemment ajoutés !

![](./images/model_card_updated_repo.png)

L'interface utilisateur vous permet d'explorer les fichiers du modèle et les commits et de voir la différence introduite par chaque commit.

**Défi 4** : C'est votre tour ! Téléchargez un modèle fictif de la bibliothèque de votre choix.

Maintenant que le modèle est dans le *Hub*, les autres peuvent le trouver ! Vous pouvez également collaborer facilement avec d'autres personnes en créant une organisation. L'hébergement via le *Hub* permet à une équipe de mettre à jour les dépôts et de faire des choses auxquelles vous êtes peut-être habitué, comme le travail en branches et le travail collaboratif. Le *Hub* permet également le versionnage de vos modèles : si un *checkpoint* du modèle est soudainement rompu, vous pouvez toujours revenir à une version précédente.

En haut du `README`, vous pouvez trouver quelques métadonnées. Vous ne trouverez que la licence pour l'instant, mais vous pouvez ajouter d'autres choses. Essayons-en quelques-unes :

```yaml
 tags:
- es       # Cela sera automatiquement détecté comme une balise de langue.
- bert     # Vous pouvez avoir des balises supplémentaires pour le filtrage.
- text-classification # Cela sera automatiquement détecté comme une étiquette de tâche.
datasets:
- llamas # Ce lien renverra à un jeu de données sur le Hub, s'il existe.
```

**Défi 5** : En utilisant la [documentation](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined), changez l'exemple par défaut dans le *widget*.

Les métadonnées permettent aux gens de découvrir votre modèle rapidement. Votre modèle apparaîtra maintenant lorsque vous recherchez des modèles de classification de texte en espagnol. Le modèle apparaîtra également lorsque vous regarderez le jeu de données.

Attendez... les jeux de données ?

## Jeux de données

Avec les pipelines d'apprentissage automatique, vous disposez généralement d'un jeu de données pour entraîner le modèle. Le *Hub* héberge environ 5000 jeux de données qui sont en libre accès et gratuits pour une utilisation dans de nombreux domaines. En plus de cela, la  [bibliothèque](https://huggingface.co/docs/datasets/) `datasets` permet d'utiliser facilement ces jeux de données, y compris les plus grands, en utilisant des fonctionnalités très pratiques comme le streaming. Ce TD ne traitera pas de la bibliothèque mais il explique comment l'explorer.

Comme pour les modèles, vous pouvez vous rendre sur [https://hf.co/datasets](https://hf.co/datasets). A gauche, vous pouvez trouver différents filtres basés sur la tâche, la licence, et la taille de l'ensemble de données.

Explorons le jeu de données [GLUE](https://huggingface.co/datasets/glue), qui est un jeu de données célèbre utilisé pour tester les performances des modèles de traitement du langage naturel.

- Comme pour les dépôts de modèles, vous avez une carte de jeu de données qui documente le jeu de données. Si vous faites défiler un peu vers le bas, vous trouverez des éléments tels que le résumé, la structure, et plus encore.

![](./images/datasets_card.png)

- En haut, vous pouvez explorer une partie du jeu de données directement dans le navigateur. Le jeu de données GLUE est divisé en plusieurs sous-jeux (ou sous-ensembles) que vous pouvez sélectionner, tels que COLA et QNLI.

  ![](./images/datasets_slices.png)

- À droite de la carte du jeu de données, vous pouvez voir une liste des modèles entraînés sur ce jeu de données.

![](./images/datasets_models_trained.png)

**Défi 6**. Recherchez le jeu de données Common Voice. Répondez à ces questions :

- Sur quelles tâches le jeu de données Common Voice peut-il être utilisé ?
- Combien de langues sont couvertes dans ce jeu de données ?
- Quelles sont les subdivisions du jeu de données ?

## Démos d'apprentissage automatique

Partager vos modèles et vos jeux de données, c'est bien, mais créer une démo interactive et accessible au public, c'est encore mieux. Les démos de modèles sont une partie de plus en plus importante de l'écosystème. Les démos permettent :

- Aux développeurs de modèles de **présenter** facilement leur travail à un large public, par exemple dans le cadre de présentations aux parties prenantes, de conférences et de projets de cours.
- D'augmenter la **reproductibilité** en abaissant la barrière pour tester un modèle.
- De partager avec un public non technique **l'impact d'un modèle**.
- Construire un **portfolio** de projets d'apprentissage automatique.

Il existe des *frameworks* Python Open-Source tels que Gradio et Streamlit qui permettent de construire ces démos très facilement, et des outils tels que [Spaces] (http://hf.co/spaces/launch) qui permettent de les héberger et de les partager. Comme TD suivant, nous recommandons de suivre le tutoriel **Créez et hébergez des démonstrations d'apprentissage automatique avec Gradio et Hugging Face**.

> Dans ce tutoriel, vous apprendrez à :
>
> - Explorer les démos créées par la communauté.
> - Construire une démo rapide pour votre modèle d'apprentissage automatique en Python en utilisant la bibliothèque `gradio`.
> Héberger les démos gratuitement avec *Spaces*.
> Ajoutez votre démo à l'organisation Hugging Face pour votre classe ou conférence.
>
> ***Durée : 20-40 minutes***
>
> 👉 [cliquez ici pour accéder au tutoriel](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/02_ml-demos-with-gradio.ipynb)
