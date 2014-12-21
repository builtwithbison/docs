---
title: Multiple Flat Rate
---

This is like single flat rate, except it's user selectable.
To use it, set `shipping_method: multiple_flat_rate` and add a `shipping_options` array that defines your options.

~~~
shipping_method: multiple_flat_rate
shipping_options:
  free:
    label: Free Shipping
    price: 0
    description: It's free, but it takes a long time.
  standard:
    label: Standard Shipping
    price: 2.50
    description: For a little extra cash, we'll tell the mailman to hurry.
~~~

By default, shipping will be set to the first option until the user selects otherwise. You can create a selection using the [shipping_options](/docs/tags/checking-out#shipping_options) tag (see below). Only `label` and `price` are required. You can add whatever else you'd like, and they will be available as variables inside the shipping options tag.