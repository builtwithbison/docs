---
title: Quantity Threshold
---
{{ noparse }}

You may specify different shipping costs depending on the number of items in the cart.  
You must specify the values in `shipping_quantity_thresholds`.

~~~
shipping_method: quantity_threshold
shipping_quantity_thresholds:
 5: 20.00     # 1-5 items,  shipping is $20.00
 10: 10.00    # 6-10 items, shipping is $10.00
 up: 0        # 11+ items,  shipping is free
~~~

{{ /noparse }}