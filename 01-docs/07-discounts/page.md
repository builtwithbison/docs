---
title: Discounts
_default_folder_template: docs
---

## Understanding discounts

A discount is a reduction of the total cart cost, calculated using a set of user defined rules.

There are two discount *concepts* in Bison:

* Site wide discounts
* Coupon codes

Both of them are created in the same way, and are exactly the same, except for one key difference:   
**A coupon code is just a discount with a `coupon_code` field.**

If a discount has a `coupon_code` field, the discount will only be applied if someone enters the code.
If it doesn't have a code, then it will apply to everyone, without them needing to do anything.

You can create as many discounts as you like, and they can all be processed together. However, customers can only use one coupon code at a time.

## Creating discounts

### Getting started
You will need to create a folder in your content directory to hold your discounts. (Default is `_content/discounts`).  

The entries should be date based. (Add `type: date` to your fields.yaml)  
The date indicates when the discounts will begin to function. You can add an `expiration_date` to your entries/fieldset to provide a date the discount will stop functioning.

### Field names
Discounts are just regular entries with a set of specifically named fields:

`discount_type`
: The short name of the discount type.  
See below for the available types.

`discount_value`
: The value of the calculation.  
ie. For a price based discount it would be dollars, for a percent based one it would be a number. For some types (ie. free shipping), a value isn't required.

`discount_priority`
: If you have multiple discounts, this determines the order. The higher the number, the earlier it's processed.

`discount_trigger_products`
: Optional. An array of product URLs that need to be in the cart for the discount to become active. Not all of them need to be in the cart.  

`discount_trigger_product_min`
: Optional. The quantity of trigger products needed in the cart for the discount to become active.  

`discount_product`
: Optional. The URL of the target product.   
In a 'buy x get y' discount type, this is the 'y'.  
Used for 'buy x get y' discount types.

`discount_product_max`
: Optional. Maximum quantity this product can be applied to.  
Used for 'buy x get y' discount types.

`coupon_code`
: Optional. If you want it to be a coupon, enter the code.

`expiration_date`
: Optional. The date the discount will stop working.

`usage_limit_type`
: Optional. The type of usage limit you want to impose on this discount. You have 3 options: `unlimited` (default), `total` or `member`.

`usage_limit`
: The number of times this discount can be used before it ceasing to work. Required when using a `usage_limit_type` of `total` or `member`.

### Fieldtype and fieldset
If you use the [fieldtype](/docs/fieldtypes/discounts), it will help you create the discount and its associated options. You won't need to look up the short name of the type or add all of the fields to your fieldset. The exception here is `expiration_date`. You will need to add a field for that.

### Locations
By default, Bison will assume your discounts (and coupons) folder is `_content/discounts`. You can change this in your [settings](/docs/configuring/settings). If you want to have separate folders for discounts and coupons, you can do that by specifying both `discounts_folder` and `coupons_folder`.


## Discount types

The following is a list of discount types currently supported in Bison. This will grow over time.

<ul>
{{ pages:listing folder="docs/discounts" }}
	<li><a href="{{ url }}">{{ title }}</a> – {{ short_desc }}</li>
{{ /pages:listing }}
</ul>

If you have a request, suggestion or requirement for a new discount type; please [get in touch](/support).


## Discount limits

You are able to restrict your discount to a certain amount of uses.

### Limit options

#### Unlimited  
This is the default. The discount can be used as many times as your customers like.

#### Total  
This will restrict the overall usage to the amount you specify.

For example, you could allow the discount to be used 10 times. Whether it's one person using it ten times, or ten people using it a single time, it doesn't matter.

#### Member  
This will restrict the usage on a per-member basis.  

For example, if you set it to 10, each member can use it 10 times. It doesn't matter how many members use it. Also note that a collective 'guest' user is tracked if you allow checkouts without membership.

### Tracking uses

Bison will track the usage of each discount to its entry.

This means that if you look at the entry file, you might see some variables that you didn't enter yourself.

`_discount_usage_count` tracks the total usage. Each time someone checks out with this discount active, this number will be increased.  
`_discount_usage` tracks the member specific usage. It contains an array of member UIDs and their corresponding usage counts. It also tracks checkouts for non-members under the `guest` key.

This won't be much to look at directly in the front-matter, but it will be displayed in a nicer format if you use the [fieldtype](/docs/fieldtypes/discounts).