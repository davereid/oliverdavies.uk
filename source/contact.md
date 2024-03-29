---
layout: default
title: Contact
meta:
  description: 'Information about how to get in touch with Oliver.'
---
{% block body_classes 'page--contact' %}

{% block content %}
# Contact

The best ways to contact me is via <a href="mailto:{{ site.email }}?subject=Contact%20Oliver%20Davies">email</a> and <a href="{{ site.twitter.url }}">Twitter</a>.

If you have a support or feature request for one of the Drupal projects that I maintain, please create an issue in the appropriate issue queue on [Drupal.org](https://www.drupal.org).

## Elsewhere

Here are some other places to find me online:

* IRC ({{ site.irc.name }}) - I'm usually in #drupal-uk and #drupal-contribute on Freenode, among others.
* <a href="{{ site.twitter.url }}">Twitter</a> (@{{ site.twitter.name }})
* <a href="{{ site.drupalorg.nice }}">Drupal.org</a>
* <a href="{{ site.linkedin.url }}">LinkedIn</a>
* <a href="{{ site.lanyrd.url }}">Lanyrd</a>
* <a href="{{ site.joindin.url }}">Joind.in</a>
* <a href="{{ site.speakerdeck.url }}">Speaker Deck</a>
* <a href="{{ site.ansible_galaxy.url }}">Ansible Galaxy</a>
* <a href="{{ site.flickr.url }}">Flickr</a>
{% endblock %}
