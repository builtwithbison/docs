---
title: Folder Structure
---

You might wonder how to set up your cart or checkout pages, especially if you are giving your client access to the control panel.
We recommend that you add the files to your `_content` folder, even if there isn't anything editable on the page.

~~~
_content/
  01-products/ 
    my-awesome-product.md             # URL: /products/my-awesome-product
    another-great-product.md          # URL: /products/another-great-product
    page.md                           # URL: /products
  page.md                             # URL: /
  cart.md                             # URL: /cart
  checkout.md                         # URL: /checkout
  order-complete.md                   # URL: /order-complete
_themes/
  my_theme/
    templates/
      utils/
        add_to_cart.html              # referenced in routes.yaml
        remove_from_cart.html         # referenced in routes.yaml
      emails/
        order_complete_admin.html     # referenced in bison.yaml
      cart.html                       # referenced in _content/cart.md
      checkout.html                   # referenced in _content/checkout.md
      order_complete.html             # referenced in _content/order-complete.md
~~~

Then your routes.yaml might look like:

~~~
routes:
  /cart/empty: bison/empty_cart
  /cart/remove: bison/remove_from_cart
~~~

and your bison.yaml might look like:

~~~
emails:
  order_complete_admin:
    enabled: true
    from: shop@mysite.com
    to: admin@mysite.com
    subject: An order has been submitted
    html_template: order_complete_admin
~~~

Of course, you can move around files in your content and templates folders, and nest them however you like to create the URL structures and folder organization paradigm that suits you.

