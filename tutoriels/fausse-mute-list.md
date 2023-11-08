---
title: Faire un feed à partir d'une fausse mute-list
description: Comment faire un feed à partir d'une fausse mute-list?
published: true
date: 2023-11-08T19:01:33.743Z
tags: customfeeds, mutelist
editor: markdown
dateCreated: 2023-10-30T17:15:11.910Z
---

# Comment faire un feed à partir d'une liste d'utilisateurs ?

Bluesky permet de créer deux types de listes : des "User Lists" (liste d'utilisateurs) ou des "Moderation Lists" (liste de modérations, anciennement appelées Mute Lists). Ces listes, outre leurs fonctionnalités respectives dans Bluesky, nous permettent de créer des listes de comptes que l'ont peut voir apparaitre dans un feed grâce à SkyFeed.

1. Créer une "User List", puis ajoutez les profils des comptes que vous voulez voir dans votre custom feed, et vous obtenez quelque chose comme [ceci](https://bsky.app/profile/rmendes.net/lists/3k2g2ic4ozk2w) 
1. De là vous allez dans Skyfeed.app, vous ajoutez un bloc "input" de type List (image 1)
1. Vous choisissez votre list via l'interface graphique (image 2 et 3)
1. Ensuite à vous de voir pour exclure les réponses, les reposts ou même ajouter un bloc input général de tout le réseau sur lequel vous faite un regex avec des mots clefs compatibles avec le thème de votre custom feed. 

<img src="https://saskeets.micro.blog/uploads/2023/bafkreia2zruwfl7qsjhij6sq33ade34l67q7srirc6aloylikgq5wv4imy.jpg" width="600" height="566" alt="">

<img src="https://saskeets.micro.blog/uploads/2023/bafkreiabpff7r3ttd5qhfjgf3jotvlobvddg457dhke2lj4r27ow5q27pi.jpg" width="600" height="553" alt="">

<img src="https://saskeets.micro.blog/uploads/2023/bafkreicwabhvxhyh3kac66fm42bwuxxci5mzqvgt55gpxq5oknjgcmr6py.jpg" width="600" height="543" alt="">

## Attention dans le cas d'un mix Liste + Input Réseau + Regex 
si vous ne voyez pas le contenu que vous voulez, changer l'ordre des blocs :
l'input du réseaux en premier, puis le regex, et enfin mettez le bloc de votre fausse-liste en dernier, 
et puis le sorting descendant ou ascendant, et vous devriez avoir ce que vous voulez. 
 
Résultat avec la fausse-liste ci dessus : mon [custom feed de news freak](https://bsky.app/profile/did:plc:tk6bkjdozskzgb47umfelfpq/feed/aaae7x6v75yog) sur bluesky !

## Épingler un post d'intro à votre liste
- pratique pour informer, inciter à participer, donner du contexte etc

[Tutos](https://saskeets.micro.blog/2023/09/01/comment-pingler-un.html) pour rajouter un bloc single post et comment le récupérer pour l'ajouter dans skyfeed. 
