---
title: Comment déployer un News Bot RSS sur Bluesky
description: 
published: true
date: 2023-10-27T19:38:52.102Z
tags: tutoriels
editor: markdown
dateCreated: 2023-10-27T19:31:42.269Z
---

# Comment apporter du contenu du web sur Bluesky?
- Un site web, un blog, une newsletter, une chaîne youtube, les possibilités sont quasi infinies mais il faut avoir un flux RSS
- toute la flotte [skyfleet](/fr/skyfleet) est propulsée par ce système
- c'est plus de 40 comptes à l'heure actuelle, certain ne sont pas configuré comme le news bot ci-dessous, comme rappelconso.skyfleet.blue ou sf.skyfleet.blue ou laune.skyfleet.blue, je ferais un autre tutoriels pour les bots à images. 

## pré-requis

- un compte bluesky dédié
- un "app password"
- un flux RSS source de contenu à publier
- [bsky.rss](https://github.com/milanmdev/bsky.rss/)
- la commande git installée
- Docker et Docker-Compose installé

<img src="https://blog.skyfleet.blue/uploads/2023/shapes-at-23-10-25-17.47.08.png" width="100%" height="" alt="">

Pour l'exercice, on va déployer un newsbot https://disclose.ngo/
C'est un média d'investigation. 

### Setup

Pas besoin d'un gros serveurs, il suffit d'avoir un ordinateur, évidemment si vous le débranché, le bot s'éteint aussi, donc, c'est plus pratique de mettre ça en ligne, sur un petit vps, même un serveur à 5€ par mois fera tout à fait l'affaire. 

Et sinon, votre machine, que ce soit sur Windows, Linux ou macOS, tout est bon !

#### un compte bluesky dédié
- Résultat de ce tuto visible sur ce bot : (sans les images parce que le site à la source ne support pas bien la technologie OpenGraph)
- [disclosengo.bsky.social](https://bsky.app/profile/disclosengo.bsky.social)
 
#### un "app password"
- gardez-le au chaud pour plus tard
 
#### un flux RSS source du contenu à publier

le site Disclose.ngo est un site sur mesure, mais il propose 2 flux RSS 

- Flux en Anglais : https://disclose.ngo/feed?lang=en
- Flux en Français : https://disclose.ngo/feed

Pour trouver le flux [RSS](https://fr.wikipedia.org/wiki/RSS ) d'un site source, l'extension [Feedbro](https://nodetics.com/feedbro/) est très utile
on pourrait faire tout un article sur cette question, mais en général, il y a toujours moyen de récupérer le flux RSS d'un site, même s'il est bien caché !

#### bsky.rss

bsky.rss est un petit bijou de code qu'on peut trouver [ici](https://github.com/milanmdev/bsky.rss/) : 

#### la commande git installée
- hors du champ de ce tuto, mais voici [l'essentiel](https://kinsta.com/fr/base-de-connaissances/installer-git-windows-macos-linux/) 

#### Docker et Docker-Compose installé
- [Installer](https://docs.docker.com/compose/install/) Docker et Docker-compose

## mise en place
Je suis sur Linux Ubuntu, donc l'approche ici part de ce principe :

### step 1

- Créer un dossier /bsky-bot/
- Cloner le dépôt à l'intérieur de ce dossier

```bash
git clone github.com/milanmdev/bsky.rss disclosengo
```
- ici "disclosengo" est le nom de votre dossier/bot à vous

### step 2
- rentrer dans le dossier via votre terminal

```bash
cd disclosengo
```

#### structure du dossier
 
##### fichier et dossier important
- docker-compose.example.yml
- data/config.example.json
- Dockerfile

```bash
ls disclosengo
```
- Vous devriez voir un dossier data, le fichier compose et le fichier data/config.json
- préparer vos fichiers de config

```bash
cp docker-compose.example.yml docker-compose.yml
```

```bash
cp data/config.example.json data/config.json
```

#### Mon compose file

Voici à quoi doit ressembler votre fichier docker-compose.yml une fois configuré

```yml
version: "3"
services:
  bsky-rss:
    restart: always # le conteneur se lance au démarrage
    image: ghcr.io/milanmdev/bsky.rss
    container_name: bsky-rss-disclosengo # le nom du container une fois qu'il tourne
    mem_limit: "256m" #mémoire limitée à
    mem_reservation: "128m" #mémoire réservée
    environment:
      - APP_PASSWORD=votre-app-password
      - INSTANCE_URL=https://bsky.social
      - FETCH_URL=https://disclose.ngo/feed?lang=en
      - IDENTIFIER=disclosengo.bsky.social
    volumes:
      - ./data:/build/data # le fameux dossier data dans le dépôt ? il sera utilisé comme volume d'écriture
```

#### Passons sur la branche de test pour bénéficier du système de file d'attente

Prendre la dernière version [ici](https://github.com/milanmdev/bsky.rss/pkgs/container/bsky.rss) 
donc à l'heure où j'écris ces lignes c'est : ghcr.io/milanmdev/bsky.rss:queue-4adef77 on va utiliser cette image docker à la place de l'image de base, donc on va remplacer l'entrée **image** ci dessous.

```yml
version: "3"
services:
  bsky-rss:
    restart: always # le conteneur se lance au démarrage
    image: ghcr.io/milanmdev/bsky.rss:queue-4adef77
    container_name: bsky-rss-disclosengo # le nom du container une fois qu'il tourne
    mem_limit: "256m" #mémoire limitée à
    mem_reservation: "128m" #mémoire réservée
    environment:
      - APP_PASSWORD=votre-app-password
      - INSTANCE_URL=https://bsky.social
      - FETCH_URL=https://disclose.ngo/feed?lang=en
      - IDENTIFIER=disclosengo.bsky.social
    volumes:
      - ./data:/build/data # le fameux dossier data dans le dépôt ? il sera utilisé comme volume d'écriture
```
Une fois ce changement fait, il suffit de sauver le fichier après avoir remplis les différents champs de la zone environnement, app password, instance url, fetch url (le rss feed) et l'identifiant. 

Si vous utilisez un domaine ça serait par exemple **skyfleet.blue** au lieu de **hande.bsky.social**
si vous avez besoin de faire tourner plusieurs flux RSS pour le même bot, il suffit de faire la mise ne place ici pour un flux et puis dupliquer tout le répertoire et changer uniquement le flux RSS. 

##### Ma config data/config.sjon

- le lien va être intégré en carte, avec image intégrée grâce à PublishEmbed
- en fonction du flux RSS, la description peut être utilisée pour générer un post plus long que juste le titre
- configurer la langue en fonction du contenu du flux RSS
- truncate c'est pour raccourcir le texte si la description est utilisée
- le runInterval c'est toutes les minutes, il va checker s'il y a du contenu à publier
- le datefield ne vous préoccupez pas avec ça pour le moment

```json
{
  "string": "$title", # post le titre
  "publishEmbed": true, # créer une carte intégrée en utilisant l'OpenGraph
  "languages": ["en"], # la langue de votre flux RSS
  "truncate": true, # coupe la description pour ne pas dépasser 300 caractères
  "runInterval": 60,
  "dateField": ""
}
```

##### Options

Quand le "publishEmbed" est en "True", il n'est pas nécéssaire d'ajouter la variable $link dans le champ string, qui correspond à ce qui va être posté, en effet la génération de la carte Embed, va se baser sur les meta OpenGraph du lien, l'image, la description et le titre qui y sont associés. 

```json
{
  "string": "$title - $link $description", # en général le titre suffit 
  "publishEmbed": true, # false déconseillé de mettre en false sauf si pas de lien
  "languages": ["en"], # fr, de, es, etc...
  "truncate": true, #false
  "runInterval": 60, # 120 absent de la branch main
  "imageField": "enclosure", # a changer par le nom de votre balise image pour l'imposer au besoin
  "ogUserAgent": "", # permet d'imposer un autre user-agent pour se faire passer pour un browser
  "forceDescriptionEmbed": "false", # true permet de forcer l'utilisation du champ description du RSS
  "descriptionClearHTML": "true", # true va nettoyer le texte de la description de balises html
  "dateField": "" # par défaut, il cherche pubDate sauf si le flux RSS n'est pas standard
}
```

### step 3

- à ce stade, vous êtes prêt pour lancer la bête !
 

## Lancement

```bash
docker-compose up
```
### D'abord le bot va remplir la file d'attente avec les posts dispo dans le flux RSS

```bash
:/home/bsky-bot/disclosengo# docker-compose up
[+] Running 1/1
 ⠿ Container bsky-rss-disclosengo  Created                                                                                                                                                                     0.2s
Attaching to bsky-rss-disclosengo
bsky-rss-disclosengo  | yarn run v1.22.19
bsky-rss-disclosengo  | $ tsx ./app/index.ts
bsky-rss-disclosengo  | [Mon, 14 Aug 2023 11:29:24 GMT] - [bsky.rss APP] Started RSS reader. Fetching from https://www.inoreader.com/stream/user/1005343511/tag/Disclosengo every 5 minutes.
[bsky.rss QUEUE] Starting queue handler. Running every 60 seconds
[bsky.rss QUEUE] Queuing item (Revealed: Perenco’s damaging oil spills in Gabon)
[bsky.rss QUEUE] Queuing item (Lützerath: French banks finance the extension of one of Europe’s largest coal mines )
```

À ce stade, le bot se déploie et vous devriez voir un retour dans votre terminal, si tout va bien, il va checker que le flux RSS et publier ce qu'il trouve à publier, ensuite le bot écrit dans un fichier txt (data/last.txt) la dernière fois qu'il a checker le flux RSS et va utiliser cette date pour comparer s'il y a du nouveau dans le flux RSS et ce toutes les 5 minutes. 

```bash
[bsky.rss POST] Posting new item (Revealed: Perenco’s damaging oil spills in Gabon)
[bsky.rss POST] Posting new item (Lützerath: French banks finance the extension of one of Europe’s largest coal mines )
 [bsky.rss QUEUE] Finished running queue. Next run in 60 seconds
[bsky.rss QUEUE] Running queue with 20 items
[bsky.rss QUEUE] Finished running queue. Next run in 60 seconds
[bsky.rss QUEUE] Running queue with 0 items
```

Vous pouvez interrompre le bot avec CTRL+C, changer la config, changer le flux RSS, bref fignoler les détails et quand vous êtes content du résultat, vous lancez le bot avec 

```bash
docker-compose up -d
```

Cela va lancer le bot comme un processus de tâche de fond. 

## Repasser sur la branche main, stable du code : 

ceci dans le fichier docker-compose.yml 
```yml
image: ghcr.io/milanmdev/bsky.rss:queue-4adef77
```
redevient :  
```yml
image: ghcr.io/milanmdev/bsky.rss
```

on sauve le fichier et on fait :

```bash
docker-compose pull
```
on vérifie bien que le fichier config.json est bien adapté à la version du code

```json
{
  "string": "$title", #vérifier la zone qui va construire le text du post
  "publishEmbed": true, #intégration des liens/images
  "languages": ["en"], #la,gues
  "truncate": true, # couper la description si trop longue
  "runInterval": 60, # si pas dans la branche queue
  "dateField": "" # champ date spécifique pour flux RSS non-standard
}
```

Bien faire attention que la dernière ligne de configuration du fichier config.json, ne doit pas comporter de virgule, mais toutes celles qui la précèdent bien !!

On lance la sauce : 
```bash
docker-compose up -d
```
vérifier l'état du bot sur laydocker ou docker logs -f nom-de-votre-container
```bash
lazydocker
```

et voilà, vous êtes en train de faire tourner la version stable du bot !



## Outils
- J'utilise [Lazydocker](https://lindevs.com/install-lazydocker-on-ubuntu/) pour explorer les conteneurs qui tournent, le log, voir si tout va bien
- [docker-ctop](https://packages.azlux.fr) est aussi pas mal pour explorer vite fait les bots qui tournent
- Il y a moyen de "mixer" plusieurs flux RSS ensemble et ainsi avoir un bot multisources, mais ça, c'est pour un autre tuto !