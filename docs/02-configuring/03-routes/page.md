---
title: Routes
---
You may want to use a handful of helper URLs such as the [add](/docs/tags/managing-the-cart/add_to_cart) and [remove](/docs/tags/managing-the-cart/remove_from_cart) from cart tags. These templates typically either require a single tag or they don't make sense to be editable and they would only clutter your control panel and/or content folder.

To get around this, you can make use of your routes file, located in `/_config/routes.yaml`

Here is an example of some common routes you might want to use:
~~~
routes:
  /cart/empty: bison/empty_cart
  /cart/remove: bison/remove_from_cart
  /cart/add: bison/add_to_cart
  /download: bison/download_file
~~~

These templates are stored in a subfolder for organization (`/_themes/your_theme/templates/bison/`), but you can change the URLs and templates to whatever you want.

You can learn more about routes in the [Statamic documentation](http://statamic.com/learn/advanced-features/routes).