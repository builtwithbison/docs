---
title: Tax-free Products
---

If you have a tax rate set, tax will be calculated based on all the products in your cart. Sometimes you will need a product to be exempt from tax.

To make a product tax-free, you just need to add a field named `tax_free` to your product with a value of `true` or `1`.

The easiest way to do this is to add a checkbox or select fieldtype to your fieldset.

```
tax_free:
  display: Tax Free
  type: checkbox
```

Notes:

* The field name can be configured using `tax_free_field`
* Statamic 1.8.2 fixes a bug where checked checkboxes can't be unchecked. Use a `select` for <1.8.2    