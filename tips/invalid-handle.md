---
title: Réparer une erreur "Invalid Handle"
description: Comment réparer un invalid handle sur Bluesky?
published: true
date: 2023-11-01T16:41:52.659Z
tags: handle
editor: markdown
dateCreated: 2023-11-01T14:00:07.041Z
---

 # Invalid Handle
 
>  Cet erreur peut aussi survenir si vous vous trompez dans la configuration de votre nom de domaine en voulant passer d'un handle.bsky.social à votre nom de domaine ou sous domaine. 
{.is-info}


Le mois dernier, Bluesky a commencé à transmettre les demandes à l'App View. 

Pour certains utilisateurs, cela a provoqué une erreur **Invalid Handle**. Si vous avez un identifiant invalide, l'interface affichera l'image ci-dessous au lieu de votre handle:

<img src="https://saskeets.micro.blog/uploads/2023/7a5f590759.jpg" width="600" height="237" alt="Invalid Handle Screenshot ">

Vous pouvez utiliser l'outil [debugging tool](https://bsky-debug.app/handle) pour résoudre le problème : 
- Tapez simplement votre handle

1. Si aucune erreur n'apparaît, essayez de mettre à jour votre handle avec celui que vous avez actuellement pour résoudre ce problème.

2. Si la page de debug affiche une erreur pour votre handle, suivez ce  [guide](https://blueskyweb.xyz/blog/4-28-2023-domain-handle-tutorial) pour vous assurer que vous l'avez configuré correctement.

3. **Revenez à votre handle.bsky.social,** mettez en ordre votre DNS avec `_atproto` ou `_atproto.handle` pour un sous-domaine et puis retenter une changement de handle une fois que le DNS est bien vérifié côté Bluesky.

4. Si cela ne fonctionne toujours pas, déposez un ticket de support via l'application (bouton " Help " dans le menu de gauche sur mobile ou de droite sur PC) et un membre de l'équipe Bluesky vous aidera.

