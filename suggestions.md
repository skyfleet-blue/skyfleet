---
title: Suggestions
description: Suggestions de sources d'informations, feedback et réclamations !
published: true
date: 2023-11-05T10:14:04.902Z
tags: skyfleet
editor: markdown
dateCreated: 2023-10-30T19:52:25.521Z
---

# Suggestions Box

> Utiliser le chat en bas à droite pour envoyer vos suggestions
{.is-info}

> Suggestions de sources d'info, media, blog, rss, newsletters etc..
{.is-success}

> Toute remarques par rapport aux bots de la [Skyfleet](/fr/skyfleet)
{.is-warning}


---

# Bug connus

## Blacklist dysfonctionelle

- un système de blacklist permet d'éviter certaine sources, réputées pour leurs désinformations par exemple, ou propagande, tel que RT, ZeroHedge ou encore des sources d'info proches de l'extrême-droite (Valeurs Actuelles, JDD etc..)

> Le système d'agrégation de contenu sur différentes thématiques [skyfleet](/fr/skyfleet) est conçu pour éviter ces sources, mais un bug a été répertorié où de temps en temps, un article se retrouve publié AVANT d'avoir été viré par les routines de la blacklist en ammont, quand c'est le cas, il s'agit d'un court moment où le bot vient précisemment chercher un nouvel article avant que le Blacklist aie éxécuté sa routine, c'est ainsi que certains compte se retrouvent parfois à publier des informations provenant de sources en blacklist. 

- Quand cela a lieu, il suffit d'alerter [@skyfleet.blue](https://bsky.app/profile/skyfleet.blue) et on fera le nécéssaire pour nettoyer le post. 

> il est prévu de travailler à l'élaboration d'une deuxième blacklist en aval, qui devrait permettre au bot de faire un check contre une list de domaine blacklisté et de skipper/passer le post si il match avec des domaines de la blacklist, mais pour l'instant c'ette idée n'est pas encore en production. 
{.is-warning}


