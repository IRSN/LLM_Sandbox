# LLM_Sandbox

Expérimentation des LLM en mode RAG sur des fiches séismes produites par l'IRSN

## Présentation du projet

L'objectif de ce projet était de créer un système de Question/Réponse en utilisant un LLM sur les fiches séismes de l'IRSN et de tester la capacité d'un LLM à extraire des données d'une fiche pour en faire de la données structurées (format Json).

Dans le cadre de cette expérimentation, nous avons donc mis en place un système de RAG (Retrieval Augmented Generation) en utilisant le framework llamaindex proposé par Meta ainsi que le LLM OpenSource Mistral-7B-Instruct-v0.1 proposé par l'entreprise Mistral et disponible sur la plateforme communautaire Huggingface.

Toutes les étapes de l'expérimentation sont disponibles dans le notebook Experimentation_LLM.ipynb. Afin de pouvoir l'utiliser il suffit de le télécharger et de suivre les installations nécessaires.

Il est conseillé de faire tourner ce Notebook sur des GPU pour être capable de faire fonctionner le modèle Mistral-7B-Instruct-v0.1.


## L'expérimentation

Notre expérimentation consiste en :
- La sélection d'un Large Language Model open source
- Le paramétrage du RAG
  - Sélection d'un Framework LLamaindex
  - Création d'embeddings
  - Paramétrage d'un retriever
  - Paramétrage d'un prompt adéquat pour notre modèle
- Évaluatution de notre RAG à travers 2 tâches distinctes
  - La capacité du modèle à répondre à une question simple et une question complexe sur l'intégralité du corpus de document
  - La capacité du modèle à créer de la donnée structurée (du JSON) en ne lui donnant qu'un seul docuement
  - 
![Texte alternatif](/data/Image3.png "Expérimentation")

### Retrieval Augmented Generation
La première expérimentation menée et testable dans ce repository est le RAG. 
Nous avons choisi de nous concentrer sur la récupération d'information dans les fiches sésimes de l'instatut.


## Arborescence

Le repository est composé de l'arborescence de documents suivante :

- data
  - input
    - embedding: représentation vecorielle des fiches séismes pour le LLM
    - fiches_seismes: fiche sésimes en format pdf
  - output
    - JSON: output de la génération de données structurées à partir des fiches séismes (expérimentation n°2)
      - json: génération de ficher json fructueuse
      - txt: génération infructueuse de fichier json = contenu généré par le LLM sans format json
    - QR: output de l'expérimentation n°1







## Installation

Pour utiliser les bibliothèques suivantes :
- llama-index
- torch
- sentence_transformers
- faiss-cpu
- pdfminer.six
- bs4
- transformers
- langchain

```python
pip install llama-index torch sentence_transformers faiss-cpu pdfminer.six bs4 transformers langchain
```


## Utilisation

Le Notebook Experimentation_LLM permet de tester les fonctionnalités que nous avons implémentées. Il se divise en 6 grandes parties.

1. **Imports et Installations:** Cette partie regroupe les différents imports de bibliothèques nécessaires à l'utilisation du notebook, avec une cellule dédiée aux installations.

2. **Paramétrage du RAG:** Permet de paramétrer un premier RAG (Retrieval Augmented Generation) avec notamment l'importation d'un modèle, ici Mistral-7B-Instruct.

3. **Sauvegarde des Réponses:** Concentrée sur la méthode de sauvegarde des réponses dans des fichiers CSV après l'appel d'un script pour automatiser l'utilisation du RAG.

4. **Extraction de Métadonnées (llamaindex):** Explicite la méthode d'extraction de métadonnées proposées par le framework llamaindex pour améliorer la partie retrival de notre RAG.

5. **Extraction de Métadonnées (personnalisée):** Similaire à la précédente mais permet d'extraire des métadonnées que nous avons extraites nous-mêmes pour obtenir de meilleurs résultats.

6. **Extraction de Données Structurées:** Code permettant de réaliser la partie extraction de données structurées à partir d'un LLM de notre expérimentation.

## Résultat

Tous les résultats de l'expérimentation sont présents dans la partie output. Vous y retrouverez :

1. **Les outputs Json:** L'expérimentation n'a pas permis d'extraire des fichiers Json dans 100% des cas. On retrouve ainsi 2 types d'outputs :
   1. Des outputs sous format json en cas d'extraction fructueuse.
   2. Des outputs sous format txt en cas d'extraction infructueuse ne respectant pas la structure du fichier json.

2. **Les outputs QR:** Notre expérimentation nous permet de générer des fichiers CSV répertoriant toutes les réponses aux questions que nous posons aux LLM sur les fiches séismes. (Voir la partie sauvegarde CSV du notebook.) Vous retrouverez ainsi les réponses dans le sous-dossier Q/R du dossier output.


## Crédits

Cécilia DAMON & Yohan MIARA

## Contribution

Cécilia DAMON
Yohan MIARA
Yann Richet

## Contact
En cas de question sur l'utilisation ou les résultats, contacter Cécilia DAMON cecilia.damon@irsn.fr


