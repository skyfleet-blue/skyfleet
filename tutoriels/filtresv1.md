---
title: Filtres V1
description: Filtrage via des mutes-lists
published: true
date: 2023-10-30T16:45:55.614Z
tags: filtrage
editor: markdown
dateCreated: 2023-10-08T17:57:41.318Z
---

comment segmenter l'activité de vos amis sur Bluesky et y exclure toute mention de Trump ou de Musk / X?

Ceci est un exemple évidemment, remplacer Musk et Trump par n'importe quel terme que vous ne voulez pas voir. 

## Étapes : 

- Vous mettez vos amis dans une fausse mute list, de laquelle vous vous désabonner (important) 
- vous utilisez cette Liste comme Input dans @skyfeed.app 
- Vous ajoutez un Block Regex avec la case **Inverse** cochée 
- Vous tapez **Trump|Musk** comme mot à exclure 
- Vous publiez votre Custom Feed et vous avez un substrat de l'activité des gens qui sont dans la liste mais sans mention de Trump ou de Musk. 


Il suffit ensuite de rajouter des gens à cette fausse mute list depuis Bluesky, jusqu'à y ajouter tous vos Follow par exemple et du coup, vous pouvez avoir un Custom Feed "Home" en contrôlant précisément ce que vous voulez ne pas voir dans votre skyline. 

Ce système peut aussi être utilisé pour, par exemple, filter des sites d'info par domaine ou bien filtrer des images avec certains mots dans le ALT etc... 


En espérant que Bluesky ajoute rapidement un système de filtre pour la Home / Following. 
