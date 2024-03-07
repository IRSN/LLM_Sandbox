# LLM_Sandbox
Expérimentation des LLM en mode RAG sur des fiches séismes produites par l'IRSN

## Présentation du projet
Dans le cadre d'une expérimentation sur les Large Language Model, nous avons mis en place un système de RAG (Retrieval Augmented Generation).
Nous nous sommes concentrés sur l'utilisation d'un modèle Open Source, Mistral-7B-Instruct-v0.1, disponible sur la plateforme communautaire Huggingface.
L'objectif de ce projet était de créer un système de Question/Réponse en utilisant un LLM sur les fiches séismes de l'irsn.
CHEMIN FICHES SEISME




## Installation

Pour utiliser les bibliothèqeu suivante :
llama-index
torch
sentence_transformers
InstructorEmbedding
faiss-cpu
pdfminer.six
install bs4

## Utilisation

Le Notebook Experimentation_LLM permet de tester les fonctionnalités que nous avons implémentées.
Il se divise en 6 grandes parties.

La première partie regroupe les différents imports de bibliothèque nécessaire à l'utilisation du notebook, avec un cellule dédiée aux installations.

La deuxième partie permet de paramétrer un premier RAG (Retreival Augmented Generation) avec notamment l'importation d'un modèle. Ici Mistral-7B-Instruct.

La troisième partie se concentre sur la méthode de sauvegarde des réponses dans des ficheirs csv après l'appel d'un script pour automatiser l'utilisation du RAG.

La quatrième partie explicite la méthode d'extraction de métadonnées proposées par le framework llamaindex pour améliorer la partie retrival de notre RAG.

La cinquième partie est similaire à la précédente mais permet, quant à elle, d'extraire des métadonnées que nous avons extraits nous même pour obtenir de meilelurs résultats

La sixième et dernière partie est le code permettant de réaliser la partie extraction de données structurées à partir d'un LLM de notre expérimentation.

