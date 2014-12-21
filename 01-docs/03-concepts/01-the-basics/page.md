---
title: The Basics
---
{{ noparse }}

Everyone has used an ecommerce site. There's 3 key parts.

* Products
* Cart
* Checkout

You have some sort of listing of products, you add one (or more) to your cart, and then you pay for them. That's about it. Let's go over how you might implement each part.

## Products
This is mostly just Statamic here.  
Use an `{{ entries:listing }}` tag pair to output products (which are just entries, after all) and links to their detail pages.

## Cart
On a product details page, you would use the [add to cart form tag](/docs/tags/managing-the-cart#add_to_cart_form) to build a form where your customer can add the product to their cart.

Now that your customer has something in their cart, you should give them a way to modify it. That's the cart page.  

You can use the [update cart form tag](/docs/tags/managing-the-cart#update_cart_form) to display the contents of the cart; and provide ways for your customer to edit the quantities, and to remove them. Or, you could use the [cart items tag](/docs/tags/viewing-the-cart#cart_items) to just display the contents without providing fields for editing.

## Checkout
Your customer has finished browsing and selecting products they want to purchase. Now you should provide a way for them to pay for what they want. You'll want to create a checkout page. You can use the [checkout form tag](/docs/tags/checking-out#checkout_form) to create a way for your customer to enter their payment details and perform a transaction. You'll need to make sure to set up a [payment gateway](/docs/gateways) in your [configuration settings](/docs/configuring/settings).

Once the payment has been completed, you'll need to provide some feedback. You can use the [order details tag](/docs/tags/checking-out#order_details) to do that.