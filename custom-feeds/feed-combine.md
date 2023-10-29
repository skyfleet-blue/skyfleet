---
title: Comment créer un feed combiné?
description: mini tuto pour créer un feed sur bluesky à partir de plusieurs sources
published: true
date: 2023-10-29T21:05:58.922Z
tags: customfeeds
editor: markdown
dateCreated: 2023-10-29T21:05:58.922Z
---

# Comment créer un feed combiné?

Imaginons un cas de figure concret, celui qui m'a occupé en partie ce soir en me posant un [colle](https://bsky.app/profile/najat.bsky.social/post/3kcw274tv3l2p)

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

- Stash 1
- Requête A
- Stash pop 1
- Requête B
- Stash 2
- Stash pop 2
- Remove duplicate
- Sort

![2023-10-29_21-46_1.jpg](/captures/2023-10-29_21-46_1.jpg)
![2023-10-29_21-47.jpg](/captures/2023-10-29_21-47.jpg)

> Donc ici on a combiné les posts du compte @africa.skyfleet.blue qui contiennent des liens vers BBC.com et vers Actualite.cd (tous les deux en rapport au Congo)
{.is-info}

> On a ajouté un nouveau bloc de tous le réseaux Bluesky, configuré sur les derniers 7 jours, de tous les posts content le mot "congo" ou toutes les images dont le ALT contien le mot congo. 
{.is-warning}

> Avant et après chaque bloc on a un stash+pop, chaque stash+pop contien un ID, dans notre cas de figure $5zxyusy pour la première requête et $ikbwj7a pour la deuxième requête, **ces blocs vont toujours ensemble**, si vous en effacez un pour recommencer la démarche, effacé sa paire pour éviter les erreurs dans Skyfeed.app
{.is-success}


- Comme l'explique très bien [@mwyann.fr](https://bsky.app/profile/mwyann.fr/post/3kcw3c7bpt32i) : 

> Stash stocke les résultats en cours pour un usage futur, et stash pop rajoute ces résultats à la sélection en cours. Donc l'idée c'est de faire une première sélection (input+regex), tu stash les résultats, puis tu fais une deuxième sélection (input+regex), et enfin tu pop + sort + remove duplicate.

## Preview

![2023-10-29_22-00.jpg](/captures/2023-10-29_22-00.jpg)

- Ici on peut voir 2 posts du bot qui pointe vers actualite.cd et qui sont en rapport avec le Congo et un post provenant du réseau qui mentionne le terme Congo. 

le [Feed](https://bsky.app/profile/did:plc:ykxvvec7hntiwmy4qk5g7kv5/feed/aaaehstriebno) est disponible ici.


Et ainsi se termine ce petit tutoriel