---
title: Custom Shipping Methods
---
{{ noparse }}

You can use a custom shipping method by entering the add-on's name.

~~~
shipping_method: bison_my_shipping_plugin
~~~

## How to build a shipping plugin

You can now build your own shipping plugins. A shipping plugin is essentially a small, appropriately named add-on.

Create `/_add-ons/bison_your_shipping_plugin/api.bison_your_shipping_plugin.php` with the following as a base:

~~~
<?php
class API_bison_your_shipping_plugin extends API
{
  public function calculateShipping()
  {
    return $price;
  }
}
~~~

If you want to provide configuration, you can create config and default files:

* `/_config/add-ons/bison_your_shipping_plugin/bison_your_shipping_plugin.yaml`
* `/_add-ons/bison_your_shipping_plugin/default.yaml`

You can use [Bison's API methods](/docs/extending-bison) to help you calculate your shipping, then just make sure `calculateShipping` returns a price (in cents).

### Example

The following is an example of a basic shipping plugin. It calculates the shipping cost by a specified percentage of the cart total.

~~~
<?php
class API_bison_shipping_percentage extends API
{
  public function calculateShipping()
  {
    $cart_items = $this->addon->api('bison')->getCartItems();
    $shipping = 0;
    foreach ($cart_items as $item) {
      $shipping += $item['price'];
    }
    $percentage = array_get($this->config, 'percentage', 10);
    return $shipping * ($percentage/100);
  }
}
~~~

{{ /noparse }}