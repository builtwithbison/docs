---
title: Price Threshold
---
{{ noparse }}

You may specify different shipping costs depending on the total cost of items in the cart.  
You must specify the values in `shipping_price_thresholds`.

~~~
shipping_method: price_threshold
shipping_price_thresholds:
 100: 20.00    # 0 to $100,       shipping is $20.00
 200: 10.00    # $100.01 to $200, shipping is $20.00
 500: 5.00     # $200.01 to $500, shipping is $5.00
 up: 0         # $500.01+,        shipping is free
~~~

{{ /noparse }}