---
layout: post
tags: git
categories: memos
title: je radote git bisect c'est top!
---

La commande git bisect permet de trouver "LE" commit qui a introduit un changement de comportement, une régression et ce, juste en ayant un pointeur sur la version "qui marche" (idcommit_ok) et un sur la référence qui "ne marche pas" (idcommit_ko).

Se positionner dans le dépôt:
- $ git bisect start
- $ git bisect good idcommit_ok
- $ git bisect bad idcommit_ko

Git va alors aider grandement au positionnement dans l'arbre pour tester et décider si oui ou non le comportement s'y trouve.
Bisecting: 40 revisions left to test after this (roughly 5 steps)

Pour chaque positionnement du pointeur, décider si le problème se trouve dans cette version (bad) ou pas (good)
- git bisect good
- git bisect bad
