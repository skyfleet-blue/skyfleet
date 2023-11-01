---
title: Utiliser les mots de passe d'application (app passwords)
description: Comment se connecter à un site Bluesky tiers sans donner son mot de passe
published: true
date: 2023-11-01T15:14:14.194Z
tags: mot de passe
editor: markdown
dateCreated: 2023-11-01T15:14:14.194Z
---

# Le principe
Lorsque vous vous connectez sur le site de Bluesky, vous utilisez votre identifiant (mail ou nom d'utilisateur), et votre mot de passe, que vous avez renseigné au moment de vous inscrire. Cependant, vous trouverez souvent, dans ce guide et sur le réseau, des liens vers des sites tiers qui vous proposeront des fonctionnalités avancées (par exemple [deck.blue](https://deck.blue), [Skyfeed](https://skyfeed.app/) ou encore [Thread Splitter](https://lemonmeant.github.io/splitter/)). Ces outils vous demanderont également de vous connecter avec un mot de passe, mais plus précisément un mot de passe d'application. Qu'est-ce que c'est ?

Un mot de passe d'application est un mot de passe généré aléatoirement par Bluesky, totalement différent de votre mot de passe actuel, et qui permet de donner un accès limité à votre compte. Notamment, avec un mot de passe d'application, il n'est pas possible de modifier votre e-mail ni votre mot de passe principal. Il n'est pas possible non plus de consulter vos codes d'invitation ni de créer d'autres mots de passe d'application.

Enfin, sachez qu'il est possible de créer autant de mots de passe d'application que vous le souhaitez. De plus, il est possible de désactiver facilement un mot de passe d'application afin de le rendre inutilisable, simplement en le supprimant. Cela constitue donc une sécurité pour votre compte, dans le cas où l'application ferait quelque chose d'imprévu ou malveillant, ou si les informations du site venaient à être dérobées.

> Si vous modifiez votre mot de passe principal, cela ne modifiera *pas* les mots de passes d'application précédemment créés.
{.is-info}

> Il est **fortement recommandé** d'utiliser un mot de passe d'application dès que vous vous connectez sur un site ou une application non officielle. Certains, par mesure de précaution, refuseront même l'utilisation d'un mot de passe principal.
{.is-warning}

> Il est également possible de se connecter au site ou à l'application Bluesky via un mot de passe d'application. Cela peut servir si vous souhaitez donner un accès limité ou temporaire à une autre personne.
{.is-info}

# Comment ça marche ?

1. Sur le site Bluesky ou sur l'application, dirigez-vous sur la page des paramètres (*Settings*), puis cliquez sur le lien *App Passwords*.

2. Cliquez sur le bouton *Add App Password*

3. Saisissez un **nom** qui vous servira à identifier à quoi va servir le mot de passe. Ce nom ne peut contenir que des lettres, nombres, espaces, tirets `-` et `_`. Il doit faire entre 4 et 32 caractères de long.

4. Cliquez sur le bouton *Create App Password*

5. L'interface va vous afficher votre nouveau mot de passe d'application, qui est présenté sous la forme de 4 blocs de 4 symboles séparés par des tirets, par exemple : `zlqa-dl2b-uyn5-fidt`. Copiez ce mot de passe en cliquant simplement dessus, et servez-vous en pour vous connecter au site tiers.

> **Attention** : une fois que vous aurez fermé la fenêtre qui affiche votre mot de passe, il ne sera plus possible de l'afficher à nouveau ! Prenez-le en note si vous comptez vous en servir à nouveau. Si vous le perdez, vous devrez en créer un nouveau.
{.is-warning}

6. La page des App Passwords vous affiche alors la liste des mots de passe d'application que vous avez créé. Pour en supprimer un, il suffit de cliquer sur la poubelle rouge à droite, et de confirmer la suppression. En quelques secondes, le site n'aura alors plus accès à votre compte.