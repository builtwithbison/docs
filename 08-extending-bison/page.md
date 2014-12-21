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
: Returns the contents of Bison's config files as an associative array.

`getCartItems()`
: Returns the contents of the cart as an associative array.

`getCustomerInfo()`
: Returns the customer's details

`getCartItemCount()`
: Returns the number of items in the cart

`toCents()`
: Converts a value to cents

`toDollars()`
: Converts a value to dollars


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