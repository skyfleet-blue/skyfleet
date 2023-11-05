---
title: Segmenter l'activité en fonction de la langue 
description: Comment utiliser un feed pour segmenter l'activité d'un compte bilingue sur Bluesky?
published: true
date: 2023-11-05T15:32:41.125Z
tags: customfeeds, langues, segmentation
editor: markdown
dateCreated: 2023-10-30T17:31:13.751Z
---

# Comment segmenter l'activité d'un compte sur bluesky par langue ?

Je n'ai pas encore fait des customs feeds segmenté par langues sur mes news bots bilingues, mais imaginons que vous avez envie de vous farcir [@Sciences](https://bsky.app/profile/sciences.skyfleet.blue) mais qu'en français pour l'exercice de ce tuto !

La recette est plutôt simple, voici les ingrédients : 

-  Un App Password que vous générez dans les paramètres de votre compte pour vous connecter sur [@skyfeeds.app](https://skyfeeds.app) 
- le DID du compte que vous voulez segmenter
- mon révélateur de [DID](https://rmdes.github.io)

1) Rendez-vous ici [DID](https://rmdes.github.io) 
2) Tapez siences.bsky.social dans le premier champ
3) vous obtenez ceci : **did:plc:56p5hqta5tnz25tucrnszplh**
<br>
<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-21-48.png" width="600" height="329" alt="">

## Étape Skyfeed.app

5) Rendez-vous sur [@skyfeeds.app](https://skyfeeds.app)
6) Connectez-vous avec votre App Password, ce mot de passe alternatif généré sur votre compte perso

## Suivre ces étapes pour segmenter l'activité d'un compte bilingue sur une langue

### 5.1 On clique sur "feed builder" à gauche, puis sur créer un Feed dans le haut de la colonne qui s'ouvre 

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-29.png" width="600" height="481" alt="">

### 5.2 vous vous retrouvez avec un exemple "Hello World' on va déjà nettoyer tout ce qu'on n'en veut pas 

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-30.png" width="600" height="590" alt="">

### 5.3 On donne un titre et on ne garde que les blocs en clair, dans l'input, on choisit Single User :  on colle l'identifiant **did:plc:56p5hqta5tnz25tucrnszplh** du compte Sciences récupéré au début du tuto. 

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-31.png" width="472" height="660" alt="">

### 5.4 on se retrouve avec ceci :  

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-32.png" width="476" height="444" alt="">

### 5.5 à cette étape, les posts affiché sont toujours en deux langues, on va s'occuper de ça.

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-32-1.png" width="600" height="584" alt="">

### 5.6 On va rajouter un Block et comme Input, on va choisir **Remove**

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-33.png" width="476" height="490" alt="">

### 5.7 là, on va choisir Language dans la liste déroulante du block remove

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-33-1.png" width="477" height="792" alt="">

### 5.8 à ce stade, c'est quasi terminé, on choisit French et le petit = barré pour dire, tout ce qui n'est pas égal à du français, on le vire du flux. 
À ce moment-là, le contenu sur la colonne de **preview** à droite n'affiche que des posts en français.
On peut sauver notre Feed à ce stade en le publiant.  

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-37.png" width="600" height="580" alt="">

### 5.9 Ici, on remplit les champs et éventuellement ajoute une image qui sera visible pour les utilisateurs ou au moment du partage du custom feed

 <img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-39.png" width="600" height="578" alt="">

### 6.0 Ici, vous avez dans l'encadré supérieur l'adresse de votre Custom Feed, c'est avec ce lien que vous pouvez le partager à d'autres personnes sur le réseau. 

<img src="https://blog.rmendes.net/uploads/2023/2023-08-29-20-42.png" width="600" height="585" alt="">
 
 ## Résultats

- Voici le [Custom Feed](https://bsky.app/profile/did:plc:tk6bkjdozskzgb47umfelfpq/feed/aaaefdfbvgixm) en question

Ceci est juste un exemple de ce qui peut être fait en termes de custom feed sur un compte, vous pourriez bien rajouter un champ regex en mentionnant uniquement vouloir recevoir des actus sur Mars ou sur le James Webb Telescope, ou uniquement les posts contenant 10 likes etc...

- Ce custom feed peut être actualisé en éditant simplement le feed et en republiant ce dernier
 les changements sont immédiats. 

- L'avantage des customs feeds sur lesquels vous avez la main, c'est que vous pouvez les changer
les améliorer etc..contrairement au custom feed sur le compte des autres. 

## Conseils

- Si vous ne voyez pas une langue sur Bluesky, c'est qu'il faut aller dans les préférences de votre compte perso et définir que vous voulez bien voir X ou Y langues sur bluesky, autrement, vous ne voyez tout simplement pas les langues qui ne sont pas activées. 

Ex: [@EUwatch](https://bsky.app/profile/euwatch.live) est tri lingues, mais si vous n'avez pas l'espagnol, et l'anglais activé sur votre compte, vous ne verrez que l'actualité en Français sur ce compte. 

L'avantage d'un custom feed segmenté, c'est que vous pouvez ne pas suivre le compte si le volume est trop important et recevoir uniquement ce qui vous intéresse, que ce soit par choix de langue ou mots clefs.