---
title: Custom data
short_desc: A simple way to view and edit custom data
---

There's no native fieldtype to view or edit arrays in the format which custom_data uses. This fieldtype will display the values in a simple editable table.

To set it up, add the following to your fieldset:

~~~
fields:
  custom_data:
    type: bison_custom_data
~~~