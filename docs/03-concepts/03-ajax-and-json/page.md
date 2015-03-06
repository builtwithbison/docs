---
title: AJAX and JSON
---
{{ noparse }}

All the really cool ecommerce sites let you add items to your cart without taking you away from what you're doing. Now you can do that with Bison.

Bison knows if you're submitting the `add_to_cart_form` or accessing the `add_to_cart` tag using an AJAX request. If you are, it'll give you some useful JSON in return, instead of redirecting you.

As of 1.4, this also applies to the `update_cart_form`.

Here's a really basic add to cart form.

~~~
{{ bison:add_to_cart_form return="/cart" attr="id:cart-form" }}
  <input type="number" name="quantity" />
  <input type="submit" value="Add to cart" />
{{ /bison:add_to_cart_form }}
~~~

You might also have a cart item count in your header.

~~~
<span id="cart-count">0</span>
~~~

Then with jQuery, you'd hijack the submission and do it yourself.

~~~
<script>
  var $form = $('#cart-form');
  $form.on('submit', function(e) {
    // Prevent the actual submission
    e.preventDefault();
    // Perform an AJAX request
    var request = $.ajax({
      url: $form.attr('action'),
      method: 'POST',
      data: $form.serialize()
    });
    // When the AJAX request is done:
    request.done(function(data){
      // The item was successfully added to the cart
      if (data.success) {
        // Update the number in the header
        $('#cart-count').text(data.cart.total_items);
        // Give some feedback
        alert('Your item was added to the cart, good job!');
      }
      // There was a problem adding the item to the cart
      // Maybe it was out of stock.
      else {
        // Display some feedback
        alert('Uh oh. There was a problem adding to cart!');
      }
    });
  });
</script>
~~~

{{ /noparse }}
