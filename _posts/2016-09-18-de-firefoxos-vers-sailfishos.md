---
layout: post
title: "De FirefoxOS à SailfishOS"
tags: firefoxos, sailfishos, nexus5
---

Si [vous avez]({% post_url 2015-11-14-smartphone-firefoxos-commande-ok%}) [tout]({% post_url 2015-12-19-rex-un-mois-firefoxos%}) [suivi]({% post_url 2016-01-02-sauvegarder-et-mettre-a-jour-firefox-os%}), j'étais depuis plusieurs mois sur FXOS sur mon Nexus5 et c'était plutôt bien. La communauté Mozilla ayant [annoncé sa fin du soutien](https://firefoxos.mozfr.org/post/2016/02/Firefox-OS-passe-des-smartphones-aux-objets-connectes) au projet FirefoxOS, je n'avais plus de mises à jour de build depuis un moment. Le prochain projet [à suivre est B2GOs](https://firefoxos.mozfr.org/post/2016/06/B2G-OS-pour-smartphones-c-est-votre-moment) !

J'avais envie de tester SailfisOS, ce n'est pas complètement libre, il n'y a pas de playstore, son interface est connue pour sa particularité d'utilisation et il existait un build pour mon tel.

J'ai clairement galéré pour l'installer, alors que [la doc est très bien faite](https://wiki.merproject.org/wiki/Adaptations/libhybris/Install_SailfishOS_for_hammerhead#Steps_to_install), il suffit de la lire et de ne pas sauter d'étape (oui, celle où ya écrit "Wipe" là ;)

J'ai tout passé avec TWRP qui est une application de flash de rom, backup, restore dans le menu "recovery" du téléphone. C'est très pratique.
```
$ fastboot flash recovery twrp-3.0.2-0-hammerhead.img
```

La couche logicielle en elle même, j'aime beaucoup pour l'instant. Passées les premières heures pour l'avoir en main, la navigation est très fluide et agréable. Concernant les store, il existe un "Jolla store" et un dépôt alternatif "OpenRepos" utilisable avec le client [Warehouse](https://openrepos.net/content/basil/warehouse). J'en suis encore à trouver mes marques avec les applications et explorer les catalogues.

Ce que j'ai gagné:

* un téléphone à l'heure au reboot
* une superbe petite app d'horloge, chronomètre, heure, décompte
* un écran que je peux tourner en mode paysage (oui, chez moi sous ffx ça ne marchait pas...)
* plus besoin de la touche "back" (avec ffos le "module" qui devait me permettre de l'utilisait ne fonctionnait pas, avec sfos je n'en ai plus besoin, ça se fait autrement)
* une interface fluide et agréable
* quelques compétences en flash de roms de téléphone.

Ce qui me manque aujourd'hui:

* une application de gps (encore et toujours...),
* un client Whatsapp qui marche (ben oui, les copines je ne vais pas leur parler de telegram ou autre... mais j'ai essayé),
* une app qui permet à mon pc de contrôler mon téléphone,
* une app qui gère bien wallabag pour lire mon flux framabag.

Affaire à suive ;)

