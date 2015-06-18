---
title: git word diff
tags:
  - drupal-planet
  - git
draft: true
---

Using `$ git diff`:

    -Oliver Davies is a <a href="{{ site.drupalorg.nice }}">Drupal Developer</a> and Linux System Administrator based in the UK. He works for the [Drupal Association](https://assoc.drupal.org) and also provides part-time consultancy services.
    +Hi, I'm Oliver Davies, a <a href="{{ site.drupalorg.nice }}">Drupal Developer</a> and System Administrator based in the Newport, South Wales. I work for the [Drupal Association](https://assoc.drupal.org), while also working freelance on Drupal websites and Linux servers.
    
Using `$ git diff --word-diff`:

    <span>{+Hi, I'm+}</span> Oliver [-Davies is-]{+Davies,+} a <a href="{{ site.drupalorg.nice }}">Drupal Developer</a> and[-Linux-] System Administrator based in the [-UK. He works-]{+Newport, South Wales. I work+} for the [Drupal [-Association](https://assoc.drupal.org) and-]{+Association](https://assoc.drupal.org), while+} also [-provides part-time consultancy services.-]{+working freelance on Drupal websites and Linux servers.+}
