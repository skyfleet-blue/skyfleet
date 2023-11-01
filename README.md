---
title: Contribuer à Skyfleet.blue
description: Comment rejoindre les contributeurs/trices du wiki et quelques principes de fonctionnement. 
published: true
date: 2023-11-01T15:37:55.755Z
tags: skyfleet
editor: markdown
dateCreated: 2023-10-17T17:50:52.947Z
---

# Skyfleet.blue
- Un wiki de ressources pour bluesky

# Collaborer avec nous pour construire le wiki : 

 - mentionnez [@skyfleet.blue](https://bsky.app/profile/skyfleet.blue) si vous souhaitez nous contacter sur Bluesky
 - contactez-nous via le système de chat sur le wiki pour être ajouté en tant que collaborateur
 - la collaboration peut être faite via GitHub ou en utilisant l'éditeur visuel du wiki


# Convention de collaboration


> Ce wiki est disponible sous la Licence du domaine public, chaque contribution peut être attribuée autant dans la façade publique que sur le github au contributeur qui apporte le contenu, le contenu est mis à disposition sous la license du domaine public dans l'esprit de construire un wiki ayant pour but de servir la communauté Bluesky
{.is-info}


> c'est une bonne pratique de faire un lien vers la source du conseil ou de l'astuce, du tutoriels vers son auteur d'orgine afin de ne pas pomper la communauté sans la créditer. 
{.is-warning}

# Arborescence des fichiers

Les pages en Français sont par défaut stockée à la racine du répertoire, les pages en Anglais ou autre dans un dossier par langue, tel que /en/ etc..
Ensuite les pages des tutoriels, custom feeds, astuces etc.. sont elle aussi dans leur propre répertoire. 

- pour mettre une page dans un répertoire il suffit de la créer ou de la sauver en la déplaçant, en choisissant préalablement le répertoire auquel on veut faire apartenir la page en question. 

c'est ce qui permet d'avoir par exemple : https://skyfleet.blue/fr/skyfleet-sources/mediasfr
- skyfleet-sources est un répertoires pour les sources des bots
- mediasfr est le nom du bot et de la page


## Images

- logo
- images
- captures

Pour uploader une image au bon endroit, il faut d'abord rentrer dans le dossier avant de téléverser l'image dans celui ci
on essaye de mettre toutes les captures d'écrans des tutos ou autre dans "captures", les images en général dans "images" et les logo ou couvertures des différents comptes de la flotte dans "logo"


# Traduction

par défaut la langue principale du wiki est le français et les traductions ou pages en Anglais vienent se loger
dans /en/nom-de-la-page pour faire la traduction d'un page existante dans le wiki, il faut faire attention de lui laisser le même SLUG en Anglais qu'en Français (original) afin que le système sache faire correspondre les traductions de pages. 


# Comment faire pour : 

## comment faire pour qu'une image s'affiche correctement lorsqu'un lien du wiki est partatgé sur bluesky ou ailleurs ? 

- cliquer sur "Page" et coller le code suivant dans l'onglet "Styles"
- changer l'image au besoin pour que le preview soit en rapport avec le tutoriel ou le lien en question.
- le code ci dessous correspond à une page par défaut pour une page générique du wiki qui permet d'afficher le titre et la description (provenant du wiki lui même) et les tags ci dessous gère la partie image de la carte opengraph.

```html
<!-- Facebook Meta Tags -->
  <meta property="og:type" content="website">
  <meta property="og:image" content="https://skyfleet.blue/images/skyfleet1.jpg">

  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image">
  <meta property="twitter:domain" content="skyfleet.blue">
  <meta property="twitter:url" content="https://skyfleet.blue">
  <meta name="twitter:image" content="https://skyfleet.blue/images/skyfleet1.jpg">

  <!-- Meta Tags Generated via https://www.opengraph.xyz -->
```




