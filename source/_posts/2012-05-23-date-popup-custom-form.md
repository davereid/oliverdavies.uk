---
title: How to add a date popup calendar onto a custom form
nav: blog
slug: add-date-popup-calendar-custom-form
tags:
  - Forms
  - Form API
  - Date
  - Calendar
  - Drupal 7
  - Drupal Planet
  - Drupal
---
First, I need to download the <a href="http://drupal.org/project/date" title="Date module on Drupal.org">Date</a> module, and make my module dependent on date_popup by adding the following line into my module's .info file.

    dependencies[] = date_popup

Within my form builder function:

~~~php
$form['date'] = array(
  '#title' => t('Arrival date'),

  // Provided by the date_popup module
  '#type' => 'date_popup',

  // Uses the PHP date() format - http://php.net/manual/en/function.date.php
  '#date_format' => 'j F Y',

  // Limits the year range to the next two upcoming years
  '#date_year_range' => '0:+2',

  // Default value must be in 'Y-m-d' format.
  '#default_value' => date('Y-m-d', time()),
);
~~~