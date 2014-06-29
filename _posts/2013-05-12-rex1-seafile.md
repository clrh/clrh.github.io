---
layout: post
title: "Rex 1 avec seafile"
description: ""
category: admin
tags: [seafile, serveur, selfhosting, sysadmin]
---

Il y a quelques jours je [blogguais]({% post_url 2013-05-09-repartir-sur-de-bonnes-bases %}) que j'avais choisi seafile pour synchroniser des dossiers entre plusieurs postes pour remplacer Dropbox.

> ### Gérer des dossiers partagés
> 
> - Objectif: sortir de dropbox et maitriser mes fichiers et l'hébergement.
> - Outil: *seafile*
> - Statut: todo
> - [site officiel](http://seafile.com)

### Pourquoi Seafile

Mes besoins au départ:
- vider mon dropbox
- avoir autant d'espace que mon serveur me le permet
- gérer plusieurs espaces pour plusieurs utilisations (pro / perso etc.)
- partager des dossiers via http avec des personnes de mon entourage
- syncrhoniser automatiquement les dossiers que j'ai choisi en fonction du pc utilisé
- open source bien sûr...

Pour choisir l'outil, ayant testé l'outil en environnement pro, je ne suis pas allée chercher plus loin. J'ai trouvé le produit assez sexy et répondant à mes besoins.

Autres solutions disponibles que l'on m'a cité:
- [sparkleshare](http://sparkleshare.org/)
- [owncloud](http://owncloud.org)

### Succès et obstacles

- Installation initiale en 15 minutes [via](https://github.com/haiwen/seafile/wiki/Download-and-setup-seafile-server)
- Blocage avec un problème de communication entre le client et le serveur "connecting server..." sans trop d'explications dans les logs :[
- Après redémarrage du client, le téléchargement des bibliothèques se fait très bien \o/
- Ce que j'aime à ce jour c'est sa facilité d'installation et d'utilisation: une fois le serveur installé, il suffit de récupérer le paquet (deb pour moi) pour le client, de l'exécuter, de se rendre sur l'interface web du serveur, de se connecter, choisir la bibliothèque (espace ou dossier) qu'on veut synchroniser en local et de le sélectionner et c'est fait. La petite applet côté client va se charger de scruter le serveur et le dossier client pour uploader ou télécharger les nouveaux éléments.
- simple et efficace


