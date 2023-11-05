---
title: Créer un Custom Feed à signets ?
description: Comment créer un Custom Feed pour y ranger des posts à ne pas oublier, bref des signets ?
published: true
date: 2023-11-05T14:59:07.816Z
tags: customfeeds, signets
editor: markdown
dateCreated: 2023-10-30T17:09:20.110Z
---

## Comment créer un custom feed à signets ?
Si vous voulez épingler des posts afin de les conserver et les retrouver plus facilement, vous aurez besoin de :
- un mot clef ou un symbole qui va vous servir de filtre
- Skyfeed.app
- 2 min de votre temps

Vous commencez par créer un nouveau custom feed sur [skyfeed.app](https://skyfeed.app) où il vous faudra 3 blocs:
1. Un bloc **Input** où vous choisissez **Single User** et vous cliquez **Select Yourself**

1. Puis un bloc **Regex** avec la requête de votre choix, par exemple : ```📌``` ou ```📍```
1. Enfin un bloc **Sort by** Creation date pour ranger vos posts par date
1. Vous pouvez ensuite publier votre custom feed

De là, à chaque post (ou repost) où vous utilisez les emoji **📍** ou **📌**, vous allez pouvoir retrouver les posts correspondants dans votre custom feed.

Dans votre **Regex bloc** si vous ajoutez à votre  émoji : `^📌` ou `📍$` 

Le symbole `^` va filter votre emoji seulement si il est en début de post et le symbole `$` seulement si votre emoji est en fin de post. Tandis que 📌 ou📍tout simple, précise que l'émoji est n'importe où dans le post. 

Avant de commencer à utiliser vos signets décidez bien du cas de figure que vous allez utiliser et gardez ce format pour vos futurs posts.

Perso j'utilise 📌 pour les tutos et j'utilise 📍 pour les astuces. J'ai donc deux custom feed qui stockent ces deux types de posts. C'est plus facile de retrouver mes posts de l'un ou l'autre format en fonction du signet.  

crédit à [@mwyann.fr](https://bsky.app/profile/mwyann.fr/post/3k6if56hw4a23) pour cette astuce !

Évidemment, cette idée peut être appliquée pour n'importe quoi d'autre en changeant les émojis filtres au besoin. 

## Résultats

- les [Tutos](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaag5kwutsasc) de SAS
- les [Tips](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaag5kgzth6vc) de SAS
- les Tutos en [Video](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaalfypz5ueak) de SAS

PS : En activant la case `reposts`, ça vous permets de simplement reposter le post d'un ami, en ajoutant 📌 ou📍pour que son post soit rangé dans vos signets. 

<img src="https://saskeets.micro.blog/uploads/2023/2023-09-03-14-41.jpg" width="600" height="629" alt="">