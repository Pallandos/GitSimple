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

La première chose à éviter, c'est un dépôt rempli de fichiers divers *inutiles* comme des images, versions tests, binaires ou dossiers inutiles. 

On proscrit donc :

- les dossiers `__pycache__` que l'on retrouve souvent dans les projets Python
- les binaires 
- les `.venv` et autres fichiers d’environnement Python
- les fichiers textes (hors `.txt`) de type `.docx` ou *word*