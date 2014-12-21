---
title: i18n
---

i18n is short for internationalization.

You can specify the formatting of your currency.  
For example, `$1,234,567.89` vs `€1.234.567,89` or `1 234 567,89,- kr`  

In `bison.yaml`, you can define the following variables:

* `thousands_separator` – To use a space as a separator, enter `' '` instead of just a space.
* `decimal_point`
* `currency_prefix` – If your currency has the sign before the number, like $100, enter `$`. This will be used in the CP price fieldtypes.
* `currency_suffix` – If your currency has the sign after the number, like 100kr, enter `kr`. This will be used in the CP price fieldtypes.