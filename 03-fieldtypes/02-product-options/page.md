---
title: Product Options
short_desc: Create a complex matrix of options
---
This field will let you specify different groups of options (sizes, colors, etc). It'll take those options and output a matrix of all the different combinations, where you can edit the SKUs and stock levels for each item.

This is what it looks like:

![Product options fieldtype](/assets/content/matrix-field.png)

The field is split into 2 parts: the groups and their options, then the resulting combinations.

In the first part, you specify your groups and their options.  
A group has a name (eg. Sizes), and each option has a name (eg. Small) and optionally a price modifier. Maybe 'Large' sizes cost a little extra.

<table>
	<thead>
		<tr>
			<th>Group</th>
			<th>Options</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Color</td>
			<td>Red, Green, Blue</td>
		</tr>
		<tr>
			<td>Size</td>
			<td>Small, Large</td>
		</tr>
	</tbody>
</table>

This would create a table with the following:

|Color|Size|SKU|Modifier|Price|Stock|
|-----|----|---|--------|-----|-----|
|Red|Small|...|...|...|...|
|Red|Large|...|...|...|...|
|Green|Small|...|...|...|...|
|Green|Large|...|...|...|...|
|Blue|Small|...|...|...|...|
|Blue|Large|...|...|...|...|

Each row/combination will have a field for SKU and stock level. If you specified a price modifier, the prices will also be calculated and shown for each combo.

An SKU is an identifier of that combination. It can be anything, as long as it is unique within that product.

To add this field to your fieldset, make sure your fieldset looks like the following:

~~~
fields:
  price:
    type: bison_price
  option_config:
    type: bison_option_matrix
    options_field: options
~~~
        
The `price` field acts like a base price. The modifiers in your configurator will add to or substract from it. You can't use the product options fieldtype without a price.

The `options_field` defines the field name of where the product combinations will be saved in your entry. In other words, once you save your entry, `option_config` will hold the groups, and `options` will hold the combinations.