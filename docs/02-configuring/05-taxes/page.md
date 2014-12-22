---
title: Taxes
---
{{ noparse }}

Bison allows you to set the tax rate for your customers carts.

This is done by setting `tax_rate` in `bison.yaml`. The value entered here should be a percentage (without the symbol).

The following would set a 10% tax rate.

```
tax_rate: 10
```

---

## Tax inclusive product pricing

By default, tax is automatically calculated and added to your cart's total.

If you need your product prices to be tax-inclusive (for example, for VAT) you can specify `tax_inclusive: true` in `bison.yaml`.

`{{ bison:cart_total }}` will either include or exclude tax depending on this setting. `{{ bison:cart_tax }}` will always display the same tax value regardless of the setting.

{{ /noparse }}