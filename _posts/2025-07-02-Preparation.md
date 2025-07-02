---
title: Préparation
date: 2025-07-01 11:03:33 +1000
categories: [Tuto]
tags:
description: Installation des pré-requis
---

# Installation et pré-requis

Ce court tutoriel sert à la mise en place des machines pour la suite des tutos. 

## Point d'attention sur le système d'exploitation

Comme expliqué en introduction, l'ensemble de ces tutos n'est pour l'instant disponible que pour Linux ou autre système UNIX (incluant MacOS), et donc **pas** pour Windows.

Pour de nombreuses raisons il n'est pas recommandé de coder sur Windows, je vous encourage donc à soit utiliser Windows Subsystem Linux (WSL) soit installer un dual boot Windows/Linux (dans un second temps car cette manipulation est plus complexe). 

> Je n'ai pas testé[^note1] ces tutoriels pour l'instant sur MacOS mais les commandes devraient être les mêmes au delà de l'installation, MacOS étant basé sur le noyau UNIX.
{: .prompt-tip}

[^note1]: N'hésitez pas à poster vos remarques/problèmes rencontrés avec MacOS dans la section [`issues`](https://github.com/Pallandos/GitSimple/issues) du dépôt.

## Requis

Pour ces tutoriels vous aurez besoin de :

- Un système d'exploitation compatible, parmi :
  - Une distribution Linux (Ubuntu, Fedora, Debian etc)
  - MacOS
  - Windows Subsystem Linux (WSL)
- **`git`** installé sur votre OS
- Un éditeur de texte de votre choix (VIM, VSCode, Notepad++ etc)
- Ce site à disposition!

Il est aussi recommandé (mais non nécessaire) d'avoir :

- Un compte GitHub
- Visual Studio Code 

Si vous avez déjà tous ces composants sur votre machine vous pouvez passer à l'étape suivante, sinon suivez les [instructions d'installation](#installation). 

> L'ensemble de ces tutoriel suppose que vous êtes familiers avec les commandes de base du système UNIX comme `cd`, `ls`, `cat` etc.
{: .prompt-info}

## Installation

### Système d'exploitation compatible

#### Windows Subsystem Linux (WSL)

***WSL*** est un programme de Windows qui permet de lancer Linux à l'intérieur de Windows. C'est un bon premier choix si vous ne voulez pas réaliser d'opérations complexes, mais ce n'est une solution simple sur le long terme. 

Suivez le tutoriel officiel de Windows : [Install WSL on Windows](https://learn.microsoft.com/en-us/windows/wsl/install).

#### Dual Boot

> Cette manœuvre est complexe et peut endommager votre ordinateur, ne la réalisez que si vous êtes conscients des risques et sauvegardez vos données. 
{: .prompt-danger}

Pour mettre en place un Dual Boot sur votre PC, suivez les instructions pour Ubuntu :

- [Vidéo](https://www.youtube.com/watch?v=qq-7X8zLP7g) 
- [Tuto officiel](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview) : choisir *Installing Ubuntu alongside another operating system* à l'étape 6

Pour d'autres distributions, se référer aux propres tutoriels. 

### Installer **`git`** 

Suivez les instructions selon votre système d'exploitation.

#### Linux

La version la plus simple d'installer **`git`** sous Linux est d'utiliser le gestionnaire de paquet intégré. Ouvrez votre terminal et entrez la commande correspondant à votre système d'exploitation.

Pour une distribution basée sur *Debian* (Debian/Ubuntu) :

```sh
sudo apt install git-all install-info
```

Pour une distribution *rpm* ou *Fedora* :

```sh
sudo dnf install git-all getopt
sudo ln -s /usr/bin/db2x_docbook2texi /usr/bin/docbook2x-texi
```

Validez les installation et vérifiez que l'installation est un succès :

```sh
git --version
```

Cette commande devrait renvoyer : 

```sh
>> git version 2.43.0
```
{: .nolineno}

avec votre version actuelle.

#### WSL

Pour ***WSL***, les instructions sont les mêmes que pour Linux, suivez simplement la distribution que vous avez installé dans *WSL*.