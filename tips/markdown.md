---
title: Liens Markdown
description: Comment faire des liens Markdown ? Tout savoir sur le support du Markdown sur Bluesky
published: true
date: 2023-10-31T12:08:03.902Z
tags: astuces, markdown
editor: markdown
dateCreated: 2023-10-22T17:07:16.085Z
---

# Comment utiliser les liens Markdown sur Bluesky ?

Avec le Markdown, il devient possible d'écrire des posts sur Bluesky qui intègrent un ou plusieurs liens vers des sites externes, mais en personnalisant le texte qui est associé au lien. On passe alors de ça :<br/>
https://bsky.app/profile/did:plc:tenurhgjptubkk5zf5qhi3og/feed/only-posts<br/>
à ça :<br/>
[Feed OnlyPosts](https://bsky.app/profile/did:plc:tenurhgjptubkk5zf5qhi3og/feed/only-posts)

Cela permet de créer des posts plus concis, d'économiser des caractères et d'améliorer la présentation de ses posts, en particulier ceux qui présentent des Custom Feeds ([Comment épingler un single post dans un custom feed ?](https://blog.skyfleet.blue/2023/09/01/comment-pingler-un.html))

Il est toujours possible de créer un lien sous forme de carte intégrée sous le post, les deux présentations sont possibles simultanément.

Exemples de posts contenant ce genre de liens : [ici](https://bsky.app/profile/rmendes.net/post/3kcbklwx5ra2f) ou [là](https://bsky.app/profile/rmendes.net/post/3kaunyqkcqr2f)

## Comment ça marche ? 

> Cette fonctionnalité n'est pas supportée par le client Bluesky officiel, il faut passer par un client tiers, voir la section *Clients supportés* plus bas.
{.is-info}

La structure est simple à mémoriser : le texte visible du lien va se placer entre crochets [ ] suivi immédiatement de l'URL HTTP entre parenthèses ( ), comme ceci :

```markdown
[texte](url)
```
Par exemple : 

```markdown
[Lien vers ce blog](https://skyfleet.blue/fr/home)
```

Ce qui donnera ce résultat : [Lien vers ce blog](https://skyfleet.blue/fr/home)

## Clients supportés

- https://deck.blue
- https://lemonmeant.github.io/splitter_beta/
- https://micro.blog
- https://blue.thread.center

## Bon à savoir

- Si vous créez un lien vers un site mais que le texte de votre lien est lui-même une URL différente, un [message](https://github.com/bluesky-social/social-app/pull/1573) s'affichera lorsque la personne cliquera sur votre lien, afin d'avertir l'utilisateur que le lien est possiblement trompeur, démonstration avec [ce post](https://bsky.app/profile/fenarinarsa.com/post/3kawkar7qk72s).
- Il est possible de tagguer "silencieusement" une personne en mettant un lien vers son profil, mais avec un texte vide, par exemple :<br/>`[](https://bsky.app/profile/rmendes.net)`<br/>De cette manière, la personne recevra une notification de mention mais elle n'apparaîtra pas dans le corps du message (le lien existera quand même dans les métadonnées du post, ce n'est donc pas tout à fait invisible non plus).
- Pour les anglophones, il existe une explication en vidéo ici : [How to use deck.blue's new Markdown link feature in Bluesky](https://www.youtube.com/watch?v=K2JPpSAyBqw)
