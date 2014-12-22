---
title: Inventory/Stock Tracking 
---

You can now track your inventory - or stock levels - whatever you want to call it. The terms are used interchangeably.

The method is different depending on the type of product.

### Basic product

A basic product is one that just has a price and optionally product modifiers. It *doesn't* use the configuration fieldtype.

To track inventory, just add a field named `stock` to your product's front-matter. (You can change the name of the field in bison.yaml using the `stock_field` variable.)

When someone checks out, this number will be reduced.

### Configured Product

A configured product is one that uses the [product options fieldtype](/docs/fieldtypes/product-options).
All the stock levels are defined per option.

You could technically do this without using the fieldtype, but it would be *a lot* of effort.

When someone checks out, the appropriate levels will be reduced.