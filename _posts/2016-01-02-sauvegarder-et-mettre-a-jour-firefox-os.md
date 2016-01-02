---
layout: post
title: "Sauvegarder et mettre à jour Firefox OS"
tags: firefoxos,flash,save,rex,notes
---

J'ai mis du temps à faire ma première mise à jour de Firefox OS. Je voulais
comprendre un peu l'imbrication des commandes, les possiblités et options qui s'offraient à moi. J'avais aussi envie de garder mes données puisque j'aurais à faire la manipulation régulièrement.

Mon objectif en écrivant ce post est de noter les étapes par lesquelles je suis passée, le résultat, ce que j'en ai ou pas compris afin de garder une trace.  Prenez donc ce billet comme des notes à ce sujet, pas plus ! Et si ça sert à quelqu'un d'autre, tant mieux...

Pour rappel du contexte, je me mets à jour sur une nightly de Firefox OS (soit la master de la 2.6) sur un Nexus 5 dans un but de [foxfooder](http://firefoxos.mozilla.community) et de profiter ;)

## Sauvegarder

### backup_restore_profile

* [Scripts écrits par l'équipe de QA](https://github.com/Mozilla-TWQA/B2G-flash-tool/)

```
local:~/B2G-flash-tool$ python backup_restore_profile.py -b
2015-12-20 14:46:03,545 - utilities.adb_helper - WARNING - adbd cannot run as
root in production builds
```

### adb pull

ADB (pour Android Debug Breidge) est un ensemble d'outils qui permettent de naviguer dans votre téléphone, de flasher, récupérer des infos, les pousser etc.

* Commandes conseillées sur irc à base de pull pour "tirer" les données du téléphone vers le pc.

```
adb pull /data/local data_local && adb pull /data/b2g data_b2g
```

En premier je connecte mon tel et je vérifie qu'il est reconnu:

```
$ adb devices
```

Ensuite je m'y connecte et liste les fichiers et dossiers avec un ls classique.

```
$ adb shell
shell@hammerhead:/ $ ls
```

La commande ci-dessous me permet de lui demander de me récupérer tout le dossier sdcard de mon device dans le dossier sdcard d'où je lance ma commande

```
$ adb pull sdcard/ sdcard
pull: building file list...
pull: sdcard/DCIM/100MZLLA/IMG_0102.jpg -> sdcard/DCIM/100MZLLA/IMG_0102.jpg
pull: sdcard/DCIM/100MZLLA/IMG_0100.jpg -> sdcard/DCIM/100MZLLA/IMG_0100.jpg
...
```

Je n'ai pas pu accéder au dossier data:

```
shell@hammerhead:/ $ ls /data/
opendir failed, Permission denied
```
Je ne peux pas non plus avoir un accès root:

```
$ adb root
adbd cannot run as root in production builds
```

En résumé, j'ai réussi à sauvegarder les données de type photos, vidéos etc. mais pas mon profil utilisateur.

* [Fil de discussion de demande d'aide sur discourse](https://discourse.mozilla-community.org/t/backup-the-phone-with-adb-permission-denied-or-adb-root-is-unavailable/6137/7)
* [Une autre option de sauvegarde](https://hacks.mozilla.org/2015/09/backing-up-user-data-on-firefox-os/)

## Mettre à jour le système

### Flasher en utilisant seulement le téléphone

* [@eyome sur framasphere me conseillait](https://framasphere.org/posts/1331312) de tout faire via le téléphone.
  * Télécharger le build via le navigateur du téléphone
  * Rebooter en mode recovery (éteindre, power et vol -, vol+/- pour sélectionner le menu recovery, power)
  * Flash zip from sdcard
  * Sélectionner le build télécharger
  * Et zou 

Je ne suis jamais parvenur au "flash zip from sdcard" puisque dès que je tente de me mettre en mode recovery, je vois un
"petit bonhomme android" couché avec la capot ouvert et un symbole "attention". Au bout de quelques minutes, le
téléphone redémarre en mode normal.

Notez que vous pouvez démarrer votre téléphone en recovery directement via votre pc:

```
$ adb reboot recovery
```

### Les mises à jour OTA (Over the air)

Si j'ai bien compris, c'est une mise à jour selon un "channel" qui est scrutée par le téléphone et proposée à l'utilisateur. Celle ci peut se faire en background tout en continuant d'utiliser le téléphone.

* [Documentation](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox_OS/Building_and_installing_Firefox_OS/Firefox_OS_update_packages#Types_of_update)

J'ai cru comprendre que le build que j'utilise ne propose pas ce type de mise à jour et que ça demande de l'adaptation.

* [Un bz](https://bugzilla.mozilla.org/show_bug.cgi?id=1224774)
* [via discourse](https://discourse.mozilla-community.org/t/backup-the-phone-with-adb-permission-denied-or-adb-root-is-unavailable/6137/7)

```
via @ nhirata

Unfortunately FOTA was not created for that build, it will have to be added into the build system to produce one.

If you're familiar with building, https://developer.mozilla.org/en-US/Firefox_OS/Building_and_installing_Firefox_OS/Firefox_OS_update_packages#Generating_a_full_FOTA_update_MAR

The trick is to implement that in our build system within taskcluster + mozharness.
```

### Flasher via mon pc

Finalement j'ai croisé les doigts et j'ai fait une mise à jour de certaines partitions (boot et system) en évitant "user" qui est la partition des données utilisateurs.

Ça m'a pris 30 secondes et j'ai gardé mes données. Mon système semble à jour, même si ce n'est pas très conventionnel comme maj. Je ne le ferai certes pas tous les jours, mais au moins une fois par semaine.

- Télécharger le build [Pour moi via firefoxos.mozilla.community](https://firefoxos.mozilla.community/device/LG/Nexus 5) [zip](https://index.taskcluster.net/v1/task/gecko.v1.mozilla-central.latest.linux.nexus-5-user.opt/artifacts/public/build/nexus-5-l.zip)
- Dézipper, connecter le téléphone en usb et lancer:

```
./flash system
./flash boot
```

### Le mot de la fin

J'ai encore passé moult temps sur des forums, à lire de la doc, farfouiller dans plusieurs sites, poser des questions de noob sans trop savoir si c'était le bon endroit pour le faire.

Je suis agréablement surprise par la réactivité de la communauté, de la disponibilité des personnes pour aider, essayer de comprendre etc. Un spécial merci à @eyome @genma @nhirata @dattaz @Porkepix & co.
