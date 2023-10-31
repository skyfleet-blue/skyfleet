---
title: Comment faire un custom feed combiné avec 2 listes in/out
description: Comment utiliser une liste pour alimenter la liste et une liste pour comme source remove?
published: true
date: 2023-10-31T13:18:32.780Z
tags: customfeeds, mute
editor: markdown
dateCreated: 2023-10-30T14:29:42.623Z
---

# Création du Feed de la Chute

Comment utiliser une mute-Liste comme source de compte approuvé pouvant poster dans le feed, tout en permettant aux utilisateurs de participer dans le feed tout en ayant un moyen de virer le bruit dans le feed ? 

## Contexte

La Chute avec William Reymond est une émission qui décrypte l'actualité américaine sur la chute de Trump et ses déboires avec la Justice. 

Il y a plusieurs comptes Bluesky faisant partie de la Team officielle, La Chute

Il y a le public sur Bluesky qui utilise les mots clefs 
- spacelachute
- lachute

Il y a le risque que des trolls puissent troller le Feed, pour se prémunir de cela, on va créer une mute list qui va nous permettre de ranger les trolls dans une liste et automatiquement enlever leurs posts du feed. 

## Création des deux listes

### la liste de la team de la chute

On va sur le profil de Willian, Cody et Thomas, ainsi que le compte officiel Lachute
et on les ajoute à une liste la Chute, en utilisant le hack des mute-listes pour avoir un liste sans restriction pour poster dans le feed. 

### Création d'une mute-list

- https://bsky.app/moderation/mute-lists

![2023-10-30_21-05.jpg](/captures/2023-10-30_21-05.jpg)

![2023-10-30_14-33.jpg](/captures/2023-10-30_14-33.jpg)

![2023-10-30_14-39_1.jpg](/captures/2023-10-30_14-39_1.jpg)


### la liste pour les trolls


On va sur le profil d'un troll et on l'ajoute à une liste, 

![2023-10-30_14-32.jpg](/captures/2023-10-30_14-32.jpg)

![2023-10-30_14-34.jpg](/captures/2023-10-30_14-34.jpg)

![2023-10-30_14-35.jpg](/captures/2023-10-30_14-35.jpg)

### On se retrouve avec deux listes
- une liste en vert pour alimenter le feed
- une liste en rouge pour virer du feed

![2023-10-30_14-36.jpg](/captures/2023-10-30_14-36.jpg)

### On se désabonne du feed en tant qu'opérateur du feed

> pour être certain de ne pas muter les trolls et bien vérifier qu'ils sont enlevé par la suite par l'ajout d'un bloc remove dans skyfeed.app
{.is-warning}


![2023-10-30_14-38.jpg](/captures/2023-10-30_14-38.jpg)

### Résultat : 

![2023-10-30_14-39.jpg](/captures/2023-10-30_14-39.jpg)

### Récapitulation


- On a créer deux mute-listes, une avec autorisation de poster, une autre mute-liste à alimenter en troll si besoin, cette dernière peut même être nettoyée tout en continuant à exister, elle nous sert comme liste de modération si besoin.

## Skyfeed.app

- Il est temps de le créer ce fameux feed !!!

![2023-10-30_14-59.jpg](/captures/2023-10-30_14-59.jpg)

### Première étape 

- on vire le bloc RegEx hello.+world et on ajoute un input list

![2023-10-30_15-01.jpg](/captures/2023-10-30_15-01.jpg)

- On se retrouve avec ça : 

![2023-10-30_15-02.jpg](/captures/2023-10-30_15-02.jpg)

- Ensuite on va ajouter un bloc Stash+Pop pour garder en mémoire les posts du bloc de la liste La Chute (112 posts dans l'image)

![2023-10-30_15-06.jpg](/captures/2023-10-30_15-06.jpg)

## Deuxième étape

- On va maintenant rajouter un bloc Remove qui va être contrôler par la liste La Chute Remove qu'on a créer auparavant. 

![2023-10-30_15-07.jpg](/captures/2023-10-30_15-07.jpg)

![2023-10-30_15-08.jpg](/captures/2023-10-30_15-08.jpg)

![2023-10-30_15-09.jpg](/captures/2023-10-30_15-09.jpg)

### Résultat et arrangement des blocs à ce stade

![2023-10-30_15-10.jpg](/captures/2023-10-30_15-10.jpg)

## Troisième étape

- On veut maintenant rajouter le public sur Bluesky, les gens qui vont utiliser les mots clefs "spacelachute" ou "lachute" et pour ce faire on a besoin d'un troisème input.

![2023-10-30_15-17.jpg](/captures/2023-10-30_15-17.jpg)

### Arrangement des blocs

- en vert ce qui rentre dans le feed de la team
- en rouge ce qu'on vire de feed via la liste la chute remove
- en vert le contenu du public
- en bleu l'ordre du stash+pop qui permet d'accumuler le contenu des différents inputs et les servir via le stash pop à la fin de la séquence.

![2023-10-30_15-20.jpg](/captures/2023-10-30_15-20.jpg)

## C'est prêt à être publié

- on a un moyen de rajouter des comptes à la liste de la team officielle
- on un moyen de rajouter des trolls à la liste la chute remove au besoin
- on a un accès pour le public à condition qu'il utilise "spacelachute" ou "lachute"

## Optimisation

- Un bloc remove language peut être ajouté pour viré tout ce qui n'est pas en Français ou en Anglais
- Un bloc remove peut être ajouté pour virer les doublons


## le Feed la Chute avec modération si nécessaire

- lien vers le feed :  
https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaafpye2nrstk
- lien vers la liste pour les trolls
https://bsky.app/profile/rmendes.net/lists/3kcxwgzf2i72r
- lien vers la liste pour la team
https://bsky.app/profile/rmendes.net/lists/3kcdxg3lfvd2o
