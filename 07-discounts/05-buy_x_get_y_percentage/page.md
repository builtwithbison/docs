---
title: Buy X Get Y Percentage Off
short_desc: Remove a percentage from an item or items in the cart.
---

{{ short_desc }}


This discount allows you to set rules involving purchasing one (or more) products, and getting a discount off a specific product (or multiple quantities of a product).

The 'X' in 'Buy X Get Y' is the trigger product.  
You can specify a selection of trigger products. A trigger product being in the cart will activate the discount. You can also set a minimum quantity.  
This will allow you to say 'buy 1 product, get x', or 'buy 10 products, get x'.

The 'Y' is the target product.  
You can specify a single target product along with the maximum discount quantity. This allows you to say 'buy x, get one free' or 'buy x, the next 2 at 50% off'.


## Examples

The following scenarios are examples of what's possible:

### Buy a painting, get a free frame

```
title: "Buy a painting, get a free frame"
discount_type: buy_x_get_y_percentage
discount_value: 100
discount_trigger_products:
  - /products/mona-lisa-painting
  - /products/birth-of-venus-painting
  - /products/the-starry-night
discount_trigger_product_min: 1
discount_product: /products/frame
discount_product_max: 1
```

* `discount_trigger_product_min: 1` is saying:  
"1 of the `discount_trigger_products` should be in the cart. It doesn't matter which one."
* `discount_product_max: 1` is saying:   
"Only apply the discount to 1 of `discount_product`. If you have more than 1 in the cart, it won't matter. Only 1 will be discounted."

### Buy 3 paintings, get 2 art class tickets for half price

```
title: "Buy 3 tickets, get the next 2 at 50% off"
discount_type: buy_x_get_y_percent
discount_value: 50
discount_trigger_products:
  - /products/mona-lisa-painting
  - /products/birth-of-venus-painting
  - /products/the-starry-night
discount_trigger_product_min: 3
discount_product: /products/art-class
discount_product_max: 2
```

* `discount_trigger_product_min: 3` is saying:  
"3 of the `discount_trigger_products` should be in the cart. It doesn't matter if it's 3 of the same, one of each, or 2 of one and 1 of another. Just 3 of any."
* `discount_product_max: 1` is saying:  
"Only apply the discount to 2 of `discount_product`. If you have more than 2 in the cart, it won't matter. Only 2 will be discounted."