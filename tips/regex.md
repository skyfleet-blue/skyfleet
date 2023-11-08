---
title: Regex ? Mais c'est quoi ce truc chelou ?
description: On entend parler de Regex sur Bluesky, mais c'est quoi cet ovni?
published: true
date: 2023-11-08T20:21:03.958Z
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

- Explication :

`/`: Les barres obliques entourent l’expression régulière.
`chaton` : Recherche le mot “chaton”.
`(ne)?` : Le `?` signifie que le “ne” est facultatif. Donc cela correspond à “chaton” ou “chatonne”.
`/g` : Le `g` signifie que la recherche doit être globale, c’est-à-dire qu’elle doit trouver toutes les occurrences dans le texte.

En utilisant ce regex, tu pourras trouver tous les mots liés aux chats ! 🐱🔍✨


Mais à quoi ça sert sur Bluesky ???

> Disons que vous avez envie d'un Feed sur les chats et bien ce regex `/chaton(ne)?/g` serait un bon point de départ, bien sûr il faudra affiner la requête, définir des mots ou des variantes que vous ne voulez pas voir, mais en utilisant le Feed Builder de https://skyfeed.xyz vous devriez être à même d'utiliser cette requete : `/chaton(ne)?/g` et de déjà voir ce qui en ressort !
{.is-info}

- Mais ça peut faire quoi d'autre en pratique un regex ? 

Bien sûr ! Les expressions régulières sont comme des détectives textuels. Elles peuvent rechercher des motifs spécifiques dans du texte. Voici quelques exemples de ce que tu peux faire avec les regex :

- Trouver des adresses e-mail :
        Si tu veux extraire toutes les adresses e-mail d’un texte, tu peux utiliser un regex comme ceci :

        [a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}

        Ce regex correspond à la structure générale d’une adresse e-mail.

    
- Valider des numéros de téléphone :
        Pour vérifier si un numéro de téléphone est bien formaté, tu peux utiliser un regex adapté à ton pays. Par exemple, pour les numéros de téléphone français :

        ^01-9{4}$

        Ce regex vérifie si le numéro commence par un zéro, suivi de 9 chiffres.

- Trouver des dates :
        Si tu veux extraire des dates d’un texte, tu peux utiliser un regex comme celui-ci :

        \d{2}/\d{2}/\d{4}

        Ce regex correspond au format de date “jj/mm/aaaa”.

- Chercher des mots spécifiques :
        Si tu veux trouver tous les mots qui contiennent “soleil”, tu peux utiliser un regex comme celui-ci :

        \bsoleil\b

        Ce regex ne correspondra qu’aux occurrences exactes du mot “soleil”.

- Nettoyer du texte :
        Parfois, tu peux utiliser les regex pour supprimer des caractères indésirables d’un texte. Par exemple, pour enlever les espaces en trop :

        \s+

        Ce regex correspond à un ou plusieurs espaces consécutifs.

Amuse-toi bien avec les expressions régulières ! Elles sont vraiment puissantes une fois que tu les maîtrises. 🕵️‍♂️🔍✨


