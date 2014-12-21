---
title: Discounts
short_desc: Makes configuring discounts easier
---

This will allow you to configure your discount without worry about all the different fields associated with each discount type.

To set it up, add the following to your fieldset:

~~~
fields:
  discount:
    type: bison_discounts
    display: Discount
~~~

This field displays a dropdown with the available discount types. Once you select a type, its options will be displayed for you.

![Discounts Field](/assets/content/discounts-field.gif)

You **don't** need to manually add the discount fields (`discount_type`, `coupon_code` etc) to your fieldset.


## Type-specific options

### Buy X, Get Y discounts
The product suggest and dropdown fields will be populated depending on your `product_folder` [configuration](/docs/configuring/settings) variable.