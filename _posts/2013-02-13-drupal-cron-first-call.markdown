---
layout: post
tags: [drupal, crons]
categories: memos
title: 1er chargement de Drupal long ? direction les crons
---

Dans une installation classique de Drupal, les crons sont déclanchés à l'appel d'une page. Une bonne pratique découverte récemment est de désactiver les crons gérés par drupal et de débrayer ce lancement dans votre crontab.

En bref:
- Désactiver poormanscron
option 1: via drush
    $ drush vset cron_safe_threshold 0

option 2: via l'UI Administration » Configuration » System » Cron


- Lancer les crons via la crontab

1/ Récupérer l'url de lancement des crons de type `http://<site>/cron.php?cron_key=<key>` dans Administration > Reports > Status Report
2/ Editer votre crontab
$ crontab -e
3/ Ajouter une ligne de ce type pour lancer les crons toutes les heures ici
`0 */1 * * * wget -O - -t 1 http://<site>/cron.php?cron_key=<key> `

Sur le net:
- http://juliendubreuil.fr/drupal/drupal-et-taches-planifiees
- http://drupal.org/cron
- http://www.trash-factor.com/content/beware-cron
- http://drupal.stackexchange.com/questions/18326/how-can-i-stop-the-cron-tasks-from-being-triggered-by-site-visitors
