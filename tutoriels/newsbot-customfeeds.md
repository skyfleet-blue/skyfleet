---
title: Comment combiner un newsbot RSS pour générer des Customs Feeds thématiques ?
description: mise en place d’utilisation des customs feeds sur Bluesky basé sur un News Bot qui va générer le contenu, ce qui va nous permettre de segmenter l’activité du newsbot en différents customs feeds auxquels les utilisateurs vont pouvoir s’abonner.
published: true
date: 2023-10-30T18:10:09.601Z
tags: customfeeds, newsbot, rss
editor: markdown
dateCreated: 2023-10-30T17:19:00.246Z
---

L'idée avec ce tuto, c'est de démontrer une mise en place d'utilisation des customs feeds sur Bluesky basé sur un News Bot qui va générer le contenu, ce qui va nous permettre de segmenter l'activité du newsbot en différents customs feeds auxquels les utilisateurs vont pouvoir s'abonner. 

- D'abord, j'ai été récupérer les [Flux RSS](https://www.lemonde.fr/actualite-medias/article/2019/08/12/les-flux-rss-du-monde-fr_5498778_3236.html
) de chez LeMonde.fr
- Ensuite, j'ai mis en place un agrégateur de flux afin de rassembler les différents flux d'info par dossier (actu, culture, planète etc..) 
- Ensuite, j'ai mis en place le newsbot en tant que tel en [suivant mon tuto](/fr/tutoriels/newsbot-rss-bluesky)


 <img src="https://blog.rmendes.net/uploads/2023/shapes.png" width="600" height="294" alt="">

## 12 flux de veilles sur un même compte bluesky

![Vue FreshRSS des catégories d'info LeMonde.fr](https://blog.rmendes.net/uploads/2023/2023-08-18-12.41.15-lemonde.rmendes.net-f127ad1d0077.jpg "Vue FreshRSS des catégories d'info LeMonde.fr")

## Comment sont construits les custom feeds ?


J'avais besoin d'une ancre stable sur lequel me baser pour chaque catégorie Le Monde et en analysant les URL's des articles Le Monde on peut constater qu'en fonction de la Section attribuée à la source, l'URL change en fonction de différent mots clef. (voir section skyfeed ci dessous)


## Résultat de la veille sur Bluesky

![Flux d'information LeMonde sur bluesky](https://blog.rmendes.net/uploads/2023/2023-08-18-11.20.59-bsky.app-47c2f830a66b.png "Flux d'information LeMonde sur bluesky")

## Skyfeed custom feed builder
Vue de la mise en place d'un custom feed avec [skyfeed.app](https://skyfeed.app)

![2023-10-30_19-03.jpg](/captures/2023-10-30_19-03.jpg)


### Chaque Feed fait un filtre sur la zone URL avec le bloc RegEx
> ça permet d'attribuer des mots clefs de base qui sont systématiquement dans l'URL de chaque article et d'ainsi segmenter le flux d'article total en différent custom feed, ce qui nous permet d'avoir culture, sports, actualités, international etc en différent feed.
{.is-info}

![2023-10-30_19-03_1.jpg](/captures/2023-10-30_19-03_1.jpg)




## Listes des custom feeds sur [@lfm.bsky.social](https://bsky.app/profile/lemonde.skyfleet.blue)
- [International](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak5xpuqt5a) 
- [Planète](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak6tv6b3wm)
- [Opinions](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak6goyuuzw)
- [France](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak5ii3hl5c)
- [Culture](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak42um3ytm)
- [Economie](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak5cxtrldw) 
- [Science](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak63b6ltpm)
- [Pixels](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak6n7hmuua) 
- [Sports](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak7d5jvnw2)
- [Guide d'Achat](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak5qr63svy)
- [M le Mag](https://bsky.app/profile/did:plc:f5mbotnuol4anbbwxwb6wnfg/feed/aaaak56aqxica) 

![Vue du compte sur bluesky](https://blog.rmendes.net/uploads/2023/2023-08-18-11.21.22-bsky.app-d481b4821bcd.png "Vue du compte sur bluesky")


## Résultats : 
![Vue Skyfeed des différents flux thématique](https://blog.rmendes.net/uploads/2023/2023-08-18-12.21.56-skyfeed.app-ba18710228bd.jpg "Vue Skyfeed des différents flux thématique")


## le problème des doublons (résolu)
Pour régler les problèmes de doublons, c'est-à-dire, un article qui apparaît dans 2 ou 3 flux, j'ai déjà viré les flux à la Une, vu qu'ils reprennent le contenu des catégories, ensuite grâce à Inoreader, je vire les doublons d'une même catégorie en faisant un tri sur les articles qui ont le même titre, mais qui sont publiées à plusieurs endroits et enfin, on utilise le flux de sortir du dossier (culture, actu, sports etc..) comme input d'entrée du bot qui veille à l'arrivée de nouvelles publications et qui s'en charge de les publier.

## Modification par la suite de la première version de ce tuto : 
Vu qu'il y avait encore des doublons, tout a été reconstruit, c'est à dire que l'agrégation de l'ensemble des flux cités ci plus haut sont rassemblé dans un seul dossier, sur lequel le check de duplicatas se fait, ainsi ça vire les doublons d'une manière transversale, sur l'ensemble de la veille. 

Ensuite pour faire la segmentation, au lieu de la faire sur des préfix qui annonce de quel catégorie vient l'article, on se base sur la structure des articles chez LeMonde pour segmenter l'information en plusieurs custom feeds : dont /internatonal/ ou /economie/ ou /culture/ dans l'URL deviennent les repères sur lesquels se fait la segmentation, résultat, plus de doublons et des customs feeds par catégories; 

Tout de même certain choix ont dû être fait, par exemple la catégorie Idées du journal ont été mise dans le segment Actualités. 