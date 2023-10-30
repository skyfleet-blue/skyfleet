---
title: Comment créer un Custom Feed à signets ?
description: Comment créer un Custom Feed pour y ranger des posts à ne pas oublier, bref des signets ?
published: true
date: 2023-10-30T17:09:20.110Z
tags: customfeeds, signets
editor: markdown
dateCreated: 2023-10-30T17:09:20.110Z
---

## Tuto Signets

- votre DID
- un mot clef qui va vous servir de filtre
- Skyfeed.app
- 2 min de votre temps

Vous commencez par créer un nouveau custom feed sur [skyfeed.app](https://skyfeed.app), à côté de ça, 
dans le bloc **Input** vous choisissez **Single User** et vous cliquez **Select Yourself**

Puis vous ajoutez un **regex bloc** avec la requête <pre>```📌```</pre> ou <pre>```📍```</pre> 
De là, vous publiez votre custom feed et chaque post (ou repost) où vous utilisez le emoji **📍** ou **📌** dans cet example, vous allez le retrouver dans votre custom feed.

Si votre  émoji est précédé comme ceci : ^📌 ou  comme cela 📍$ 

ça va faire le filtre, le match en fonction du fait que l'émoji est au debut du post ou à la fin du post.

tandis que 📌 ou📍tou simple, précise que l'émoji est n'importe où dans le post. 

Ne prenez pas tout, choisissez un cas de figure et ensuite utiliser ce format lorsque vous composez vos post et que vous voulez le garder en signet. 

Perso j'utilise 📌 pour les tutos et j'utilise 📍 dans le bloc regex pour les astuces, résultat j'ai deux custom feed qui stock ces deux types de posts et je n'ai plus à y penser, j'ai facile à retrouver mes posts de l'un ou l'autre format/type de signet.  

crédit à [@mwyann.fr](https://bsky.app/profile/mwyann.fr/post/3k6if56hw4a23) pour cette astuce !

Évidemment, cette idée peut être appliquée pour n'importe quoi d'autre en changeant les émojis filtres au besoin. 

## Résultats

- les [Tutos](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaag5kwutsasc) de SAS
- les [Tips](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaag5kgzth6vc) de SAS
- les Tutos en [Video](https://bsky.app/profile/did:plc:gc7pqgc337bwj2n5mbnkixzk/feed/aaalfypz5ueak) de SAS

ps: en activant le cas sur les reposts, ça vous permet de simplement reposter le post d'un ami, en ajoutant 📌 ou📍pour que son post soit rangé dans vos signets. 

<img src="https://saskeets.micro.blog/uploads/2023/2023-09-03-14-41.jpg" width="600" height="629" alt="">