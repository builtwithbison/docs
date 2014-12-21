---
title: Product blueprints
---
{{ noparse }}

An interesting feature of Bison is the ability to create a product blueprint (or template) and then create on-the-fly products out of it.

This is best explained with an example.

Let's say you're running a photography website where you sell different sized prints of all your photos. You sell each photo in multiple sizes on canvas or multiple sizes printed in frames.

Photo of a bird  
- 4x6" Frame ($5.00)  
- 8x10" Frame ($10.00)  
- 11x14" Canvas ($20.00)  
- 16x20" Canvas ($40.00)

Here you can see that one photo has multiple types and prices. If all of your photos are being sold in the same configurations, it will be a lot of work to add 4 (or more!) options for each photo.

A solution would be to use a product blueprint.

You could create one product blueprint which would be the basis for all your photography products. Call it something like 'Photo'.

Then you could leverage a combination of Statamic's [get_files](http://statamic.com/learn/documentation/tags/get_files) tag and Bison's [add_to_cart_link](/docs/tags/managing-the-cart/add_to_cart_link) tag to create all of the products on the fly. You can drop all the photos into a folder, and using those two tags, create a complete product selection.

~~~
{{ get_files in="assets/photos" }}
  <a href="{{ bison:add_to_cart_link product='/products/photo' price='5' extra='photo:{file}|type:frame|size:4x6' }}">4x6" Frame</a>
  <a href="{{ bison:add_to_cart_link product='/products/photo' price='10' extra='photo:{file}|type:frame|size:8x10' }}">8x10" Frame</a>
  <a href="{{ bison:add_to_cart_link product='/products/photo' price='20' extra='photo:{file}|type:canvas|size:11x14' }}">11x14" Canvas</a>
  <a href="{{ bison:add_to_cart_link product='/products/photo' price='40' extra='photo:{file}|type:canvas|size:16x20' }}">16x20" Canvas</a>
{{ /get_files }}
~~~

Bison usually only allows a product to be added to the cart once. If you re-add it, it'll just increase the quantity. With the `extra` parameter, it makes Bison see the same product as different products.

So now you've created 4 separate products for each image you loop through using the get_files tag. It adds up very quickly!

{{ /noparse }}