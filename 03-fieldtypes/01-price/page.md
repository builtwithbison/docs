---
title: Price
short_desc: Adds a currency mask
---
This adds a currency mask to your field. It will prevent the user from entering inappropriate data. It will also obey your i18n settings.

To set it up, add the following to your fieldset:

~~~
fields:
  price:
    type: bison_price
    display: Price
~~~