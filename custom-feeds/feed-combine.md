---
title: Comment créer un feed combiné?
description: mini tuto pour créer un feed sur bluesky à partir de plusieurs sources
published: true
date: 2023-10-29T22:36:53.080Z
tags: customfeeds
editor: markdown
dateCreated: 2023-10-29T21:05:58.922Z
---

# Comment créer un feed combiné?

Imaginons un cas de figure concret, celui que m'a posé cette [colle](https://bsky.app/profile/najat.bsky.social/post/3kcw274tv3l2p), on veut un feed qui prend des posts du réseaux et en même temps qui prend certains post d'un compte qui post sur le Congo. 

## Contexte : un [feed](https://bsky.app/profile/did:plc:ykxvvec7hntiwmy4qk5g7kv5/feed/aaaehstriebno) sur le Congo par [@najat](https://bsky.app/profile/najat.bsky.social)

- On veut récupérer les [posts](https://bsky.app/search?q=congo) du réseaux Bluesky qui parle du Congo
- On a un bot [@Africa.skyfleet.blue](https://bsky.app/profile/did:plc:zryecagiz2pfjw2f27twv7h6) dont certains posts, pas tous, sont des posts provenant de deux sources d'info sur le Congo 
-- BBC.com
-- Actualite.cd

On veut pas tous les posts du bot, car ils concernent d'autres pays d'Afrique, d'autres sites d'actu, du coup on va utiliser un bloc input "Single User" pour le bot et bloc input "entire network" pour capter les post en rapport au congo sur tout le réseau.

## Pré requis pour construire le feed

- le [DID](https://rmdes.github.io/) du compte ci dessus :  **did:plc:zryecagiz2pfjw2f27twv7h6**
- des mots clefs en rapport avec le congo : **Congo** 

## Skyfeed.app


- Requête A
- Requête B
- Stash 2
- Stash pop 2
- Remove duplicate
- Sort

> Comme l'explique très bien [@mwyann.fr](https://bsky.app/profile/mwyann.fr/post/3kcw3c7bpt32i) : 
Stash stocke les résultats en cours pour un usage futur, et stash pop rajoute ces résultats à la sélection en cours. Donc l'idée c'est de faire une première sélection (input+regex), tu stash les résultats, puis tu fais une deuxième sélection (input+regex), et enfin tu pop + sort + remove duplicate.


![2023-10-29_23-30.jpg](/captures/2023-10-29_23-30.jpg)
![2023-10-29_23-30_1.jpg](/captures/2023-10-29_23-30_1.jpg)

> Donc ici on a combiné les posts du compte @africa.skyfleet.blue qui contiennent des liens vers BBC.com et vers Actualite.cd (tous les deux en rapport au Congo)
{.is-info}

> Après le premier bloc, la requête A, on ajoute un bloc Stash, ça va nous permettre d'ajouter la requête B, mais de garder les posts de la requête A dans le Feed, et avec le Stash Pop à la fin, ça nous permet de tout joindre et d'avoir les posts des deux requêtes.
{.is-success}

> On a ajouté un nouveau bloc de tout le réseaux Bluesky, configuré sur les derniers 7 jours, de tous les posts contenant les mots **congo** et **DRC** (on aurait aussi pu inclure les ALT contentant ces même mots) 
{.is-warning}

## Preview

![2023-10-29_22-00.jpg](/captures/2023-10-29_22-00.jpg)

- Ici on peut voir 2 posts du bot qui pointe vers actualite.cd et qui sont en rapport avec le Congo et un post provenant du réseau qui mentionne le terme Congo. 

le [Feed](https://bsky.app/profile/did:plc:ykxvvec7hntiwmy4qk5g7kv5/feed/aaaehstriebno) est disponible ici.


## Optimisation

- C'est pas une bonne pratique de mettre des tas de bloc pour chaque requête, il faut optimiser le preview du feed pour qu'il s'affiche le plus rapidement possible
![2023-10-29_22-58.jpg](/captures/2023-10-29_22-58.jpg)
- Donc par exemple ici, si je voulais rajouter le mot RDC, il suffirait de changer le RegEx actuel comme par exemple : `\bcongo\b|\bRDC\b` sans rajouter un nouveau bloc regex.

## RegEx

En utilisant l'expression régulière `\bcongo\b`, vous créez une expression qui correspond à une chaîne de caractères qui contient le mot "**congo**" comme un mot entier, c'est-à-dire qu'il doit être entouré par des limites de mots ou des espaces blancs.

Voici ce que font les parties de cette regex :

`\b` est un ancre de limite de mot (word boundary en anglais). Elle ne correspond pas à un caractère lui-même, mais elle représente une position dans la chaîne de caractères où un mot commence ou se termine. Elle permet de s'assurer que "**congo**" est un mot entier et n'est pas inclus dans un mot plus long. Par exemple, il ne correspondra pas à "Congolais" car le "o" est entouré de lettres.

  `congo` est la séquence de caractères que vous recherchez.

`\b` est une autre ancre de limite de mot qui assure que "congo" se termine bien comme un mot entier.

Ainsi, `\bcongo\b` correspondra à des occurrences de "**congo**" lorsqu'il est entouré de limites de mots ou d'espaces blancs, mais il ne correspondra pas à des occurrences de "congo" au milieu d'autres mots. Par exemple, il correspondra à "Le Congo est un pays" mais pas à "Congolais".

le `|` permet de délimiter chaque mots clefs et d'en rajouter à la suite dans le même bloc RegEx
ainsi `\bcongo\b|\bRDC\b` va faire un match avec des posts contenant le mot entier **congo** ou **DRC**