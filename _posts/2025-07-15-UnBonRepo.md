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

## Les X règles

### 1 - Ne garder que le nécessaire

La première chose à éviter, c'est un dépôt rempli de fichiers divers *inutiles* comme des images, versions tests, binaires ou dossiers inutiles. Dans le monde de l'open source, on propose des fichiers lisibles, donc on ne met pas de binaires et autres fichiers compilés dans un dépôt : c'est l'utilisateur qui compilera. **`git`** se charge de l'historique de versions, donc on ne met pas des fichiers de tests : on teste les fonctionnalités dans des branches. On ne met pas non plus de fichiers propres à l’exécution du code, comme des `__pycache__` ou les fichiers d’environnement. 

De manière générale, on ne met que les codes sources du projet, les fichiers configurations ou les licences, mais rien d'autre.

On proscrit donc :

- les éléments propres à l'exécution locale (comme les `__pycache__` )
- les binaires 
- les `.venv` et autres fichiers d’environnement
- les fichiers textes (hors `.txt`) de type `.docx` ou *word*

### 2 - Le `.gitignore` est obligatoire

Pour satisfaire facilement la règle précédente, il faut prendre soin d'écrire un bon fichier `.gitignore`. C'estun fichier doté d'un format spécial, qui va définir quels sont les fichiers que **`git`** ne doit pas traiter. Il se compose d'expressions rationnelles. 

> Lorsque vous créez un dépôt sur GitHub, vous pouvez choisir d'inclure un `.gitignore` basé sur *template*. Choisissez le langage principal de votre projet. Cela évite d'avoir un créer de toutes pièces un fichier complexe. 
> 
> ![...](/assets/img/gitignore.png)
{: .prompt-tip}