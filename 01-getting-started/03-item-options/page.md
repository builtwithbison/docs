---
title: Item options and price modifiers
---
## Basics
Products can have options, like colors or sizes.

You have two options:

 * Use YAML (or a Grid field in the CP) to create a single group of options
 * Use the [product options fieldtype](/docs/fieldtypes/product-options) in the CP to create a complex matrix of options and manage stock levels.

## Using YAML

If you would like your products to have options, like colors or sizes, add an option field (field name is configurable) to your entries' YAML front-matter.  
This field should contain an array of options.

~~~
price: "100.00"
options:
  - Red
  - Blue
  - Green
~~~

Each option can have the ability to modify the base price by specifying an addition or subtraction amount.
To take advantage of price modifiers, your options field should contain an associative array like this:

~~~
title: Big Knife
price: "100.00"
options:
  - 
    label: Regular handle
    modifier: "0.00"
  - 
    label: Gold handle
    modifier: "20.00"
  - 
    label: No handle
    modifier: "-30.00"
~~~

In this example, the knife with a regular handle would be $100, a gold handle would be $120 and no handle would be $70.  

Price modifiers *modify* the price, they don't set it.

## Control panel

If you are using the control panel, setting up this field can be done very easily using the [Grid fieldtype](http://statamic.com/learn/documentation/fieldtypes/grid).

~~~
options:
  type: grid
  display: Options
  min_rows: 0
  fields:
    label:
      type: text
      display: Color
    modifier:
      type: bison_price
      display: Price
~~~

![Item options](/assets/content/item-options-field.png)

## Advanced

If you want greater control over options, check out the [product options matrix fieldtype](/docs/fieldtypes/product-options). This will allow you to do the same as above, and more! You can create multiple option groups (size, color, etc) and maintain stock levels for each configuration.