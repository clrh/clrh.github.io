---
layout: post
title: "Silent Grouping et Estimation agile"
description: ""
category: agile 
tags: [rex, agile, estimation]
---

## Contexte

Dans une démarche agile, vous pouvez rapidement vous retrouver avec un énorme backlog qu'on vous demande d'estimer. Une des options est d'y passer des jours, voire des semaines à spécifier et des jours encore à estimer, rediscuter le périmètre etc. Cependant, vous conviendrez que à ce stade du projet, ce n'est pas ça qui va apporter de la valeur, mais avoir une estimation grosse maille qui donne une idée de l'enveloppe et de l'effort global nécessaire. J'avais entendu parler de certaines pratiques avec des promesses fantastiques quand au débit d'estimation des stories: extreme quotation ou encore silent grouping. En voici mon retour d'expérience avec première mise en pratique.

## Résultat

* 151 stories estimées en 58 minutes à 3

## Que s'est il passé ?

### Phase 1

* Timebox 45 minutes
* 151 cartes représentant chacune une story sont empilées sur un coin de la table :"en tant que <> je peux <> afin de <>"
* Un tableau avec pour colonne une valeur de carte de planning poker est matérialisée sur une grande table, bien sûr l'unité est le point
* En silence, chaque personne à tour de rôle prend une carte, la place dans une colonne du tableau
* En 22 minutes, toutes les cartes sont posées

* Répartition à la fin de la première phase (colonne: nombre de cartes):

|Valeur estimation |Nombre de stories|
|------------------|-----------------|
|infini| 10|
|? | 24|
|20| 2 |
|13| 6 |
|8 | 5 |
|5 | 15|
|3 | 31|
|2 | 30|
|1 | 25|
|0 | 3 |

### Phase 2

* Timebox 45 minutes
* En silence, chacun peut faire le choix de déplacer les stories, une à une (si pas de consensus, la story est retirée pour discussion ultérieure)
* Résultat: 45 min de dispo, reste 26 min à la fin

### Phase 3

* Debrief 10/15 min
* Chacun avec sa cuoleur de stabilo fait un point quand il ne sait pas de quoi retourne la story qui est dans un chiffre
** 10 stories identifiée par une personne, 6 par une autre et 4 avec 2 couleurs
** soit 12 stories estimées non comprises sur 117

## Debrief de l'équipe

### Qu'en avez vous pensé ?

* "C'est rigolo"
* Une personne est moins convaincue par la 2e phase, car il n'a pas osé redéplacer si une personne déplace une fois => "si on peut pas en parler ça a moins d'intérêt"
* "C'est bien bien rapide ce qui permet un gros tri "immédiat""
* CH contente d'avoir expérimenté "c'est qu'une heure"
* Moins de 10 % des stories estimées qui ne sont pas comprises
* Taux de confiance sur l'estimation avec ce qu'on sait (=que les titres) entre 3.5 et 4 / 5

### Problèmes / interrogations rencontré(e)s

* "On a que le titre"
* Parfois le titre ne suffit pas à savoir ce que c'est donc encore moins à savoir combien ça coûte
* Il y avait peut être des doublons ou stories qui se recouppent
* Ambiguïté sur la recherche (lié au contexte: recherche que avec search api ou pz ou les 2)

#### Améliorations

* forcer la consigne de la "bataille" sur la 2e phase
* setup très important, à anticiper plus
* acheter du scotch "papier" pour les lignes du tableau
* PO sur place dans le silent grouping, au moment où les devs étaient dans la même ville, le product owner était en déplacement

### Pour aller plus loin

* http://systemagility.com/2011/05/22/using-silent-grouping-to-size-user-stories/
* http://blog.octo.com/extreme-quotation-planning-agile-sous-steroides/
