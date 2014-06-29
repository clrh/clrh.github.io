---
layout: post
title: "Drupal coding standards"
description: "drush dcs, drupalcs and vi"
category: 
tags: [drupal, dev]
---

## Command line install

http://drupal.org/project/drupalcs

<pre>
$ export DRUPALCS_DIR=/drupal_code_sniffer/install/path
$ sudo pear install PHP_CodeSniffer
$ cd $DRUPALCS_DIR
$ wget http://ftp.drupal.org/files/projects/drupalcs-7.x-1.0-beta1.tar.gz
$ tar xzf drupalcs-7.x-1.0-beta1.tar.gz
$ sudo ln -sv $DRUPALCS_DIR/Drupal $(pear config-get php_dir)/PHP/CodeSniffer/Standards/Drupal
$ mkdir -p ~/.drush/drupalcs
$ cp $DRUPALCS_DIR/drupalcs.drush.inc ~/.drush/drupalcs/
</pre>


## Install for VIM

<pre>
$ cd ~/.vim
$ wget -O syntastic.zip http://www.vim.org/scripts/download_script.php?src_id=17476
$ unzip syntastic.zip
</pre>

Adds this line in .vimrc:

<pre>
let g:syntastic_phpcs_conf=" --standard=Drupal --extensions=php,module,inc,install,test,profile,theme"
</pre>

## Use it

### In your drupal installation
<pre>
$ drush dcs file_or_directory
</pre>

### In vim editor

By default, syntax is verified at each save, to display the error window you can do:
<pre>
:SyntasticCheck
:Errors
</pre>

More help:
<pre>
:helptags ~/.vim/doc
:h syntastic
</pre>
