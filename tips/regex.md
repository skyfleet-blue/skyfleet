---
title: Regex ? Mais c'est quoi ce truc chelou ?
description: On entend parler de Regex sur Bluesky, mais c'est quoi cet ovni?
published: true
date: 2023-11-08T20:13:42.650Z
tags: regex
editor: markdown
dateCreated: 2023-11-08T20:13:42.650Z
---

# Définition Niveau 0
Imagine que tu as une boîte magique remplie de lettres et de chiffres. 🎩✨

Eh bien, les expressions régulières (ou **regex**) sont comme des baguettes magiques pour chercher des motifs spéciaux dans cette boîte. 🪄✨

Par exemple, si tu veux trouver tous les mots qui commencent par “chat”, tu peux dire à ta baguette magique : “Hé, baguette, trouve-moi tous les mots qui commencent par ‘chat’ !” 🐱✨

Et pouf, la baguette magique te montrera tous les mots comme “chaton”, “chatouiller” ou “chatonner”. 🐾✨

En gros, les regex sont des outils géniaux pour chercher des choses spécifiques dans du texte, comme des mots, des adresses e-mail ou même des numéros de téléphone ! 📝🔍✨

Voici un exemple de regex pour trouver des mots comme “chaton”, “chatouiller” ou “chatonner” dans du texte :

`/chaton(ne)?/g`

Explication :

`/`: Les barres obliques entourent l’expression régulière.
`chaton` : Recherche le mot “chaton”.
`(ne)?` : Le `?` signifie que le “ne” est facultatif. Donc cela correspond à “chaton” ou “chatonne”.
`/g` : Le `g` signifie que la recherche doit être globale, c’est-à-dire qu’elle doit trouver toutes les occurrences dans le texte.

En utilisant ce regex, tu pourras trouver tous les mots liés aux chats ! 🐱🔍✨


Mais à quoi ça sert sur Bluesky ???

Disons que vous avez envie d'un Feed sur les chats et bien ce regex `/chaton(ne)?/g` serait un bon point de départ, bien sûr il faudra affiner la requête, définir des mots ou des variantes que vous ne voulez pas voir, mais en utilisant le Feed Builder de https://skyfeed.xyz vous devriez être à même d'utiliser cette requete : `/chaton(ne)?/g` et de déjà voir ce qui en ressort !
