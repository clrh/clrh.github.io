---
layout: post
tags: drupal
categories: memos
title: Coder, Ventral.org, PAReview.sh - revue de code automatisée pour Drupal
---

Nous avons pour objectif de contribuer notre premier module. J'ai donc pris conaissance des pratiques Drupal:
- http://drupal.org/node/1068952 Promoting sandbox projects to full pro
- http://drupal.org/node/1011698 Applying for permission to create full projects

Autres pages qui me semblent des pages de références dans le dev Drupal
- http://drupal.org/node/360052
- http://drupal.org/coding-standards
- http://api.drupal.org/api/drupal

J'ai refais un tour ce week end sur certains outils de revue de code automatisée au #dclyon.

- Coder est un module de revue de code qui s'installe et se pilote via l'interface Configuration > Coder
http://drupal.org/project/coder

  drush dl coder
  drush en coder_review

- Ventral.org est un site de revue en ligne qui se base sur un script (PAReview.sh) 
http://ventral.org/pareview
http://drupal.org/project/pareviewsh

   drush dl en pareviewsh
   drush dl drupalcs
   sudo aptitude install php-pear
   sudo pear install PHP_CodeSniffer
   sudo ln -s /path/to/drupal/sites/all/modules/drupalcs/Drupal /usr/share/php/PHP/CodeSniffer/Standards/Drupal
   ./pareview.sh ../module_a_revoir/

#drupal #note #capitaliser #codereview
