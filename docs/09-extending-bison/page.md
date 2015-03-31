---
title: Extending Bison
---

You can now interact with Bison through your own add-ons through two options: API and Hooks.

## API
Bison has a number of API methods for you to tap into.

Use any of the following methods by doing the following from any aspect of your add-on. (Core, hooks, tasks, etc)

~~~
$this->addon->api('bison')->methodName()
~~~

`getBisonConfig()`  
Returns the contents of Bison's config files as an associative array.

`getCustomerInfo()`  
Returns the customer's details

`getCartItems($use_dollars = false, $use_separator = false)`  
Returns the contents of the cart as an associative array.

`getCartItemCount()`  
Returns the number of items in the cart

`getCartSubtotal($use_dollars = false, $use_separator = false)`  
Returns the cart subtotal before discounts

`getCartSubtotalIncDiscounts($use_dollars = false, $use_separator = true)`  
Returns the cart subdotal including discounts

`getCartShipping($use_dollars = false, $use_separator = true)`  
Get the cart's shipping total

`getCartDiscount($use_dollars = false, $use_separator = true)`  
Get the cart's discount total

`getTaxRate()`  
Get the tax rate

`getCartTax($use_dollars = false, $use_separator = true)`  
Get the cart's tax total

`toCents($dollars)`  
Converts a value to cents

`toDollars($cents, $separate_thousands = false)`  
Converts a value to dollars

### Parameters

Money is handled in cents. Most of the time, you'll need values in cents. For instance, `$123,000.50` is `12300050` cents. But if you need them in dollars, set the `$use_dollars` parameter to `true`. This will give you a value with a decimal point. ie `123000.50`. If you want the thousands separated, specify that too. You will then get something like `123,000.50` or `123.000,50` depending on your currency settings.


## Hooks
Bison also runs a number of hooks at appropriate times. (Well, just one for now).

You can leverage the hook by creating the following in your `hooks.addon_name.php` file.

~~~
function bison__hook_name($parameter) {
  // do stuff
}
~~~

`bison__checkout_complete`
: This is called when a checkout has completed. You have access to the order details in the first parameter.

`bison__action_links`
: Add a button to the order details page in the CP. You should return a `<li><a href="">...</a></li>` here. You have access to the order data in the first parameter.


## More!
If you have a need for more API methods or hooks, please [get in touch](/support).