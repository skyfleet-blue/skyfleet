---
title: Regex ? Mais c'est quoi ce truc chelou ?
description: On entend parler de Regex sur Bluesky, mais c'est quoi cet ovni?
published: true
date: 2023-11-08T23:32:55.126Z
tags: regex
editor: markdown
dateCreated: 2023-11-08T20:13:42.650Z
---

# Définition de base
## Imagine que tu as une boîte magique remplie de lettres et de chiffres. 🎩✨

Eh bien, les expressions régulières (ou **regex**) sont comme des baguettes magiques pour chercher des motifs spéciaux dans cette boîte. 🪄✨

Par exemple, si tu veux trouver tous les mots qui commencent par “chat”, tu peux dire à ta baguette magique : “Hé, baguette, trouve-moi tous les mots qui commencent par ‘chat’ !” 🐱✨

Et pouf, la baguette magique te montrera tous les mots comme “chaton”, “chatouiller” ou “chatonner”. 🐾✨

En gros, les regex sont des outils géniaux pour chercher des choses spécifiques dans du texte, comme des mots, des adresses e-mail ou même des numéros de téléphone ! 📝🔍✨

Voici un exemple de regex pour trouver des mots comme “chaton” ou “chatonne” dans du texte :

[`/chaton(ne)?/g`](https://regex101.com/r/yNAODF/1)

### Explication :

`/`: Les barres obliques entourent l’expression régulière (dans des langages comme javascript, autres langages autres moeurs).
`chaton` : Recherche le mot “chaton”.
`(ne)?` : Le `?` signifie que le “ne” est facultatif. Donc cela correspond à “chaton” ou “chatonne”.
`/g` : Le `g` signifie que la recherche doit être globale, c’est-à-dire qu’elle doit trouver toutes les occurrences dans le texte.

En utilisant ce regex, tu pourras trouver tous les mots liés aux chats ! 🐱🔍✨


## Mais à quoi ça sert sur Bluesky ???

> Disons que vous avez envie d'un Feed sur les chats et bien ce regex `/chaton(ne)?/g` serait un bon point de départ, bien sûr il faudra affiner la requête, définir des mots ou des variantes que vous ne voulez pas voir, mais en utilisant le Feed Builder de https://skyfeed.xyz vous devriez être à même d'utiliser cette requete : `/chaton(ne)?/g` et de déjà voir ce qui en ressort !
{.is-info}

## OK, Mais ça peut faire quoi d'autre en pratique un regex ? 

Les expressions régulières sont comme des détectives textuels. Elles peuvent rechercher des motifs spécifiques dans du texte. Voici quelques exemples de ce que tu peux faire avec les regex :

- Trouver des adresses e-mail :
Si tu veux extraire toutes les adresses e-mail d’un texte, tu peux utiliser un regex comme ceci :

        [a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}

Ce regex correspond à la structure générale d’une adresse e-mail.

- Trouver des url :
Si tu veux extraire les urls de sites web dans un texte, on peut partir de quelque chose comme :

        (https?://)\w+(\.\w+)*\.\w{2,}
    
- Valider des numéros de téléphone :
Pour vérifier si un numéro de téléphone est bien formaté, tu peux utiliser un regex adapté à ton pays. Par exemple, pour les numéros de téléphone français :

        ^0\d{9}$

Ce regex vérifie si le numéro commence par un zéro, suivi de 9 chiffres.

- Trouver des dates :
Si tu veux extraire des dates d’un texte, tu peux utiliser un regex comme celui-ci :

        \d{2}/\d{2}/\d{4}

Ce regex correspond au format de date “jj/mm/aaaa”.

> Attention, il va aussi trouver les formats de date mm/jj/aaaa. Son utilisation est donc fortement dépendante du contexte.
{.is-warning}

- Chercher des mots spécifiques :
Si tu veux trouver tous les mots qui contiennent “soleil”, tu peux utiliser un regex comme celui-ci :

        \bsoleil\b

Ce regex ne correspondra qu’aux occurrences exactes du mot “soleil”.

- Nettoyer du texte :
Parfois, tu peux utiliser les regex pour supprimer des caractères indésirables d’un texte. Par exemple, pour enlever les espaces en trop :

        \s+

Ce regex correspond à un ou plusieurs espaces consécutifs.

Amuse-toi bien avec les expressions régulières ! Elles sont vraiment puissantes une fois que tu les maîtrises. 🕵️‍♂️🔍✨


# En résumé 

Reprenons à zéro. Imagine que tu as une boîte à outils magique. 🧰✨

Dans cette boîte, il y a un outil spécial appelé “Expression régulière” ou “regex” en abrégé. C’est un peu comme une baguette magique pour le texte ! 🪄✨

Voici comment ça fonctionne :

## Trouver des motifs :

Imagine que tu as un grand livre rempli de phrases et de mots. Parfois, tu veux trouver des choses spécifiques dans ce livre, comme tous les noms de fleurs ou tous les numéros de téléphone.
        
 Eh bien, les regex sont là pour ça ! Ils te permettent de chercher des motifs particuliers dans le texte. Par exemple, tu peux dire à ton outil regex : “Hé, trouve-moi tous les mots qui commencent par `soleil` !” ☀️🔍
 
 Et pouf, il te montrera tous les mots comme “soleil”, “ensoleillé” ou “soleil levant”.

- Des règles spéciales :

Les regex ont des règles spéciales pour décrire ces motifs. Par exemple, le point `.` signifie “n’importe quel caractère”, l’astérisque `*` signifie “zéro ou plus de fois”, et les crochets `[ ]` te permettent de spécifier des choix.

Par exemple, le regex `s[ou]leil` correspond à “soleil” ou “souleil”.


## Utilisations pratiques :

Les regex sont utilisés dans beaucoup de domaines, pas seulement en informatique. 

Par exemple :

- Nettoyer du texte : Si tu as une liste de noms avec des espaces en trop, tu peux utiliser un regex pour les enlever.

- Valider des données : Comme vérifier si un numéro de téléphone est bien formaté.
- Rechercher dans des documents : Comme chercher tous les mots “important” dans un rapport.

- Pas besoin d’être un expert :

>Tu n’as pas besoin d’être un génie de l’informatique pour utiliser les regex. Il suffit de connaître quelques règles de base et tu pourras déjà faire des choses intéressantes !
{.is-info}

En résumé, les regex sont des outils magiques pour trouver des motifs dans le texte. Alors, la prochaine fois que tu cherches quelque chose dans un livre ou un document, pense à ta baguette regex ! 📖🔮✨

# Des outils pour aller (beaucoup) plus loin

## Présentation 

- MetSem#37 : [Introduction aux expressions régulières](https://metsem.hypotheses.org/1240) (regex) (Jean-Baptiste Pressac, Pierre-Guillaume Prigent et Sébastien de Villèle, Université de Bretagne Occidentale) 

## Liens Utiles

Cinq outils et un jeux pour s'acclimater au Regex et les manipuler au mieux sur [skyfeed.app](https://skyfeed.app)

- [AutoRegex.xyz](https://autoregex.xyz/) utilise une IA pour générer tes regex
- [Regex101](https://regex101.com/) la bible du regex
- [Regex-Generator](https://regex-generator.olafneumann.org/) un générateur de regex visuel
- [RegExr](https://regexr.com/) RegExr est un outil en ligne pour apprendre, construire et tester des regex
- [RegexCrossword](https://regexcrossword.com/) un jeu pour apprendre le regex

Dans la langue de Shakespeare :
- [rexegg](https://rexegg.com) si les Annales du Disque-Monde avaient un cours de regex
- [regular-expressions](https://regular-expressions.info) là on entre chez le maître des potions

> Attention, le **service Skyfeed.app pour Bluesky** ne supporte pas toutes les requêtes Regex, certaines requête trop complexes et qui serait impossible à servir à des milliers de Feeds ne sont pas permise, ça ne veut pas dire que "ça ne marche pas", ça veut dire que Skyfeed est intentionellement limité pour ne pas crasher le service. 
{.is-warning}

## Astuces Skyfeed.app

> à faire ? :smiley:
{.is-info}

- Utiliser plusieurs mots, inutile de rajouter plusieurs bloc regex, dans la majorité des cas un bloc suffit largement pour les mots à inclure et un bloc (avec la case **inverse** cochée) pour les mots à ne pas inclure dans le feed.
  Le caractère spécial `|` permet de délimiter des alternatives.

          chat|chiens|tigre

- `\b` est un délimiteur spécial qui va trouver les emplacements de début et fin de mot. `\bchat` permettra de trouver tous les mots commençant par `chat`, mais pas `entrechat`.

- Les parenthèses permettent de grouper des schémas. Elles peuvent être utilisées pour éviter la répétition des délimiteurs par exemple. Ainsi, si vous cherchez toutes les ocurrences des mots `chat` et `félin`, vous pouvez utiliser `\b(chat|félin)\b`.