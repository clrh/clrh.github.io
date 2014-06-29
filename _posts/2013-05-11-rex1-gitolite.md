---
layout: post
title: "Rex 1 avec gitolite"
description: "La première pierre que j'ai posé avec Gitolite"
category: admin
tags: [gitolite, serveur, selfhosting, sysadmin]
---

Il y a quelques jours j'avais choisi gitolite pour héberger mes dépôts.

> ### Gestion des dépots git
> 
> - Objectif: Gérer mes dépôts sans forcément tout montrer. J'utilise aujourd'hui github dès que j'ai besoin de pousser quelque chose, plus ou moins temporaire...
> - Outil:  *gitolite*
> - Statut: Installé, reste à prendre bien en main et à utiliser massivement !
> - [tutorial](http://www.bigfastblog.com/gitolite-installation-step-by-step)
> - [site officiel](http://gitolite.com/gitolite/)

### Pourquoi Gitolite

Mes besoins (non priorisés) étaient:
- créer autant de dépôts que je voulais
- rendre des dépôts privés ou semis-privés
- tuner des droits par groupes ou utilisateurs
- ne pas payer pour un service hébergé
- héberger la solution
- apprendre un nouvel outil (parce que oui, pas besoin d'installer autre chose que git-core et ssh pour gérer tout ça)

J'ai d'abord twitté: _@clrh Comment gérez vous vos dépôts git privés ?_

Sur les réponses que j'ai eu, les outils suivants ont été cités, en voici la répartition:
- bitbucket (3)
- gitolite (2)
- gitlabhq (2)
- gitorious (1)
- github payant (1)
- sans rien (1)

Gitolite ayant été utilisé dans mon entreprise et au vu des outils cités, j'ai d'abord tenté l'expérience avec lui. J'ai estimé à ce moment du choix, que ce qui m'apportait le plus de valeur n'était pas de concurrencer et tester l'install du top 3, mais d'en prendre un des trois et de lui donner sa chance. Ca fait quelques jours que ça tourne, affaire à suivre :)

### Succès et obstacles

- Installation initiale très rapide
- J'ai un peu galéré car je n'avais pas compris les principes de bases de fonctionnement
- J'ai ensuite refais l'install avec ce [tutorial](http://www.bigfastblog.com/gitolite-installation-step-by-step) et en 10 minutes c'était parti pour de bon !

