---
layout: post
title: "De SailfishOS à CyanogenMod - dégoogliser les contacts"
tags: sailfishos cyanogenmod
---

Je continue l'aventure... Certains [manques avec SailfishOS]({% post_url 2016-09-18-de-firefoxos-vers-sailfishos %}) me font essayer autre chose dès maintenant: CyanoGenMod. Un de mes souhait est de ne pas utiliser le play store de Google... Reste donc [F-Droid](f-droid.org) qui est un catalogue d'applications libres pour android.

# Dégoogliser les contacts

Mes mails et contacts sont sur Google et jusqu'à maintenant ça allait bien. Je peux facilement synchroniser mes mails, mais pour les contacts, je ne trouve pas immédiatement. Je tente donc de trouver une solution alternative.

Mon besoin:
* Synchroniser mes contacts dans une application web et dans mon téléphone, dans les 2 sens.

[Framagenda](http://framagenda.org) permet de consulter et de partager ses agendas, mais aussi ses carnets d’adresses et ses listes de tâches.
* L'interface est sobre et agréable
* L'utilisation le semble aussi.

Framagenda repose sur le logiciel libre [Nextcloud](nextcloud.com) qui a son client sur FDroid. Pour synchroniser les informations il faut un client CalDAV. J'ai choisi de tester [DAVdroid](https://davdroid.bitfire.at). Mon compte est ensuite lié dans Paramètres > Comptes > DAVDroid.

Il faut savoir que [Framadrive](http://framadrive.org) fournit aussi un service de serveur de gestion de contacts propulsé par [Owncloud](https://owncloud.org/).
