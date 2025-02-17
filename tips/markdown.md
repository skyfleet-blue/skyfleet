---
title: Liens Markdown
description: Comment faire des liens Markdown ? Tout savoir sur le support du Markdown sur Bluesky
published: true
date: 2024-12-24T17:28:58.471Z
tags: astuces, markdown
editor: markdown
dateCreated: 2023-10-22T17:07:16.085Z
---

# Comment utiliser les liens Markdown sur Bluesky ?

Avec le Markdown, il devient possible d'écrire des posts sur Bluesky qui intègrent un ou plusieurs liens vers des sites externes, mais en personnalisant le texte qui est associé au lien. On passe alors d'un lien qui ressemble à ça :

> https://bsky.app/profile/did:plc:tenurhgjptubkk5zf5qhi3og/feed/only-posts

Qu'on peut transformer comme ceci :

> [Feed OnlyPosts](https://bsky.app/profile/did:plc:tenurhgjptubkk5zf5qhi3og/feed/only-posts)

Cela permet de créer des posts plus concis, d'économiser des caractères et d'améliorer la présentation de ses posts, en particulier ceux qui présentent des Custom Feeds ([Comment épingler un single post dans un custom feed ?](https://blog.skyfleet.blue/2023/09/01/comment-pingler-un.html))

Il est toujours possible de créer un lien sous forme de carte intégrée sous le post, les deux présentations sont possibles simultanément.

Exemples de posts contenant ce genre de liens : [ici](https://bsky.app/profile/rmendes.net/post/3kcbklwx5ra2f) ou [là](https://bsky.app/profile/rmendes.net/post/3kaunyqkcqr2f)

## Comment ça marche ? 

> Cette fonctionnalité n'est pas prise en charge par le client Bluesky officiel, il faut passer par un client tiers, voir la section *Clients compatibles Markdown* plus bas.
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

## Clients compatibles Markdown

À l'heure actuelle, ni le site ni l'application officielle Bluesky ne permet l'usage de cette syntaxe. Il faut alors passer par l'un de ces sites tiers, en n'oubliant pas d'utiliser un [mot de passe d'application](./app-passwords) pour y accéder :

- https://deck.blue
- https://lemonmeant.github.io/
- https://micro.blog
- https://blue.thread.center

## Bon à savoir

- Si vous créez un lien vers un site mais que le texte de votre lien est lui-même une URL différente, un [message](https://github.com/bluesky-social/social-app/pull/1573) s'affichera lorsque la personne cliquera sur votre lien, afin d'avertir l'utilisateur que le lien est possiblement trompeur, démonstration avec [ce post](https://bsky.app/profile/fenarinarsa.com/post/3kawkar7qk72s).
- Pour les anglophones, il existe une explication en vidéo ici : [How to use deck.blue's new Markdown link feature in Bluesky](https://www.youtube.com/watch?v=K2JPpSAyBqw)
