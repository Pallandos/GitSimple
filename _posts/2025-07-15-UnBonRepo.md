---
title: "Bien structurer son projet"
date: 2025-07-15 20:40:02 +1000
categories: [Savoir]
tags: débutant
description: Quelles sont les règles et normes pour créer un bon dépôt
---

## Introduction

Bien structurer son projet (et donc son dépôt) est un élément tout simplement nécessaire. Loin d'être un simple détail, un projet bien structurer permettra à quiconque de prendre en main le code très rapidement, donc d'être compris simplement et donc d'être efficace. 

[Martin Fowler](https://www.martinfowler.com/), un développeur et écrivain britannique a dit :

> “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” 

L'idée est donc simple : votre code doit être compréhensible par quiconque, et donc cela passe par la qualité et la structure générale de votre dépôt. 

Nous allons aborder à travers quelques règles et conseils comment maintenir un projet de manière efficace, avec l'aide de **`git`** et des hébergeurs de version (comme *GitHub*).

## Les 3 règles

### 1 - Ne garder que le nécessaire

La première chose à éviter, c'est un dépôt rempli de fichiers divers *inutiles* comme des images, versions tests, binaires ou dossiers inutiles. Dans le monde de l'open source, on propose des fichiers lisibles, donc on ne met pas de binaires et autres fichiers compilés dans un dépôt : c'est l'utilisateur qui compilera. **`git`** se charge de l'historique de versions, donc on ne met pas des fichiers de tests : on teste les fonctionnalités dans des branches. On ne met pas non plus de fichiers propres à l’exécution du code, comme des `__pycache__` ou les fichiers d’environnement. 

De manière générale, on ne met que les codes sources du projet, les fichiers configurations ou les licences, mais rien d'autre.

On proscrit donc :

- les éléments propres à l'exécution locale (comme les `__pycache__` )
- les binaires 
- les `.venv` et autres fichiers d’environnement
- les fichiers textes (hors `.txt`) de type `.docx` ou *word*

#### Le `.gitignore` est donc obligatoire

Pour satisfaire facilement la règle précédente, il faut prendre soin d'écrire un bon fichier `.gitignore`. C'est un fichier doté d'un format spécial, qui va définir quels sont les fichiers que **`git`** ne doit pas traiter. Il se compose d'expressions rationnelles. 

> Lorsque vous créez un dépôt sur GitHub, vous pouvez choisir d'inclure un `.gitignore` basé sur *template*. Choisissez le langage principal de votre projet. Cela évite d'avoir un créer de toutes pièces un fichier complexe. Vous pouvez voir tous les templates sur [ce dépôt](https://github.com/github/gitignore).
> 
> ![...](/assets/img/gitignore.png)
{: .prompt-tip}

> Un poste sera écrit pour décrire spécifiquement comment fonctionne un `.gitignore`
{: .prompt-info}

### 2 - Grouper les fichiers par leur logique

Il est important de pouvoir rapidement comprendre à quoi servent les fichiers. Cela passe évidemment par un nommage correct, tout comme à l'intérieur même du fichier. Mais il est aussi très important de bien répartir le code source dans des sous dossiers *logiques*.

Par exemple dans le projet suivant : 

```
mon-projet/
├── main.py
├── utils.py
├── test_main.py
├── test_utils.py
├── requirements.txt
├── README.md
```

On peut voir que toutes les fonctions sont mélangées : les tests, le `main`, les fonctions auxiliaires (`utils`). Il faut donc structurer tout de manière logique, en séparant les fonctions. Par exemple :

```
mon-projet/
├── mon_projet/           # Code source principal
│   ├── __init__.py
│   ├── main.py
│   └── utils.py
├── tests/                # Tests unitaires
│   ├── test_main.py
│   └── test_utils.py
├── requirements.txt      # Dépendances
├── README.md             # Documentation
```

Ces exemples sont donnés en Python mais cela reste vrai dans n'importe quel language : séparez les codes par leur **logique**. D'un côté les tests, de l'autre le code source, ce dernier séparant les fichiers en fonction de leur logique. 

#### Des fichiers bien découpés

Cela peut être vu comme une sous règle de la précédente : il faut absolument éviter les fichiers gigantesques avec 5 ou 6 fonctions. Essayez de garder les fichiers courts, en général avec une seule grande fonction ou plusieurs petites. Par exemple, une seule grande fonction peut être découpées en plusieurs sous fonctions, toutes dans le même fichier. 

En général, un seul fichier doit avoir une fonction, pas plus d'une centaine de ligne afin de pouvoir être lu d'un seul coup par un humain.

Essayez donc d'utiliser au maximum la mécanique d'*import* du langage pour avoir des fichiers digestes. 

### 3 - Présenter son projet dans un `README`

Enfin, vous avez probablement remarqué que la première chose que l'on voit sur un dépôt est le *README*. C'est un fichier qui présente le projet dans son ensemble. On y retrouve toutes les informations nécessaires à son utilisation comme :

- l'utilité de l'outil
- comment l'installer (éventuellement ses dépendances)
- comment l'utiliser

Ces 3 catégories me semblent nécessaires mais on peut aussi y inclure le code de conduite, les auteurs, comment contribuer etc...

Un `README` est écrit en Markdown (`.md`), un langage de balisage très simple et très largement utilisé aujourd'hui. 

Voici une liste de ressources pour apprendre Markdown :

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) : un bilan court de la syntaxe Markdown
- [Documentation officielle de GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) : la documentation de Markdown, par GitHub
- [Markdown tools](https://github.com/dhyeythumar/awesome-readme-tools) : une liste d'outils (avancés) pour Markdown

## Bilan

En suivant ces 3 règles, vous êtes (presque) certains de créer un dépôt qui soit lisible, facile à prendre en main (pour vous et les autres) et conformes aux usages de la communauté!