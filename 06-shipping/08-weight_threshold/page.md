---
title: Weight Threshold
---
{{ noparse }}

You may specify different shipping costs depending on the total weight of items in the cart.  
You must specify the values in `shipping_weight_thresholds`.

Bison doesn't care about what weight unit you use, as long as you're consistent.  
ie. `10` could mean 10lbs, 10kg or even 10µg.

~~~
shipping_method: weight_threshold
shipping_weight_thresholds:
 10: 5.00      # up to 10lbs,       shipping is $5.00
 20: 10.00     # then up to 20lbs,  shipping is $10.00
 30: 20.00     # then up to 30lbs,  shipping is $20.00
 up: 50.00     # then 30lbs and up, shipping is $50.00
~~~

You can specify the field name that contains your weights with `weight_field`.  
By default, Bison looks for a `weight` field.

{{ /noparse }}