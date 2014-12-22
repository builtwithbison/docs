---
title: Settings
---

Bison's configuration file can be found in `/_config/add-ons/bison/bison.yaml`.  
It provides a number of sensible defaults (shown below the descriptions) but there are also some settings you will need to tend to before beginning.

### Options

`encryption_key`<br /><small>Required</small>
: Used to encrypt and decrypt data. You should set this to a strong 32 character passphrase. You can use an app like 1Password to generate one.

`currency`
: Currency used in payment gateway.  
  <small>`USD`</small>

`product_folder`
: The folder which contains your product entries.  
If your products are located in multiple folders, you can use an array.   
eg. `['products', 'things']`  
  <small>`products`</small>

`unique_field`
: The field to determine the products' uniqueness. (title, url, or a custom field like sku for example)  
  <small>`title`</small>

`price_field`
: The field name of the prices in your products  
  <small>`price`</small>

`option_field`
: The field name of the product options / price modifiers  
  <small>`options`</small>

`tax_rate`
: Tax applied to cart (percentage)  
  <small>`0`</small>

`tax_inclusive`
: Do product prices include tax?  
  `true` will not add tax to the cart total. `false` will.  
  <small>`false`</small>

`tax_rate_field`
: Field name for overriding the tax rate on a product level  
  <small>`tax_rate`</small>

`tax_free_field`
: Field name for flagging a product as tax-free  
  <small>`tax_free`</small>

`shipping_method`
: Shipping calculation method. [More info](/docs/configuring/shipping).

`payment_gateway`<br /><small>Required</small>
: Payment Gateway handle. Gateway specific settings can be found in the [Gateways](/docs/gateways) section.

`order_save_to_file`
: Orders can be saved to file  
  <small>`true`</small>

`order_save_path`
: Location (from root) to save orders    
  <small>`_content/orders/`</small>

`order_extension`
: Filename - if you plan on displaying on the frontend, use md.  
  <small>`md`</small>

`order_id_prefix`
: A string prepended to the start of the order ID

`order_id_suffix`
: A string appended to the end of the order ID

`order_statuses`
: An array of statuses you want to use for your orders. The first in the list will be the default. It can either be key/value pairs of name/label, eg. `paid: Paid`; or a regular list, eg. `- paid`.  
  <small>`paid`</small>

`order_status_colors`
: The colors used in the control panel (but you can also use them in your templates with the [order_status](/docs/tags/checking-out/order_status) tag). This should be a key/value pairing of order statuses and colors. They can be any valid CSS color (hex, rgb, etc)  
  <small>`paid: green`</small>

`email_handler`
: The email handler used to send any emails. By default, PHP Mail will be used, but Bison can integrate with the following services:  
  [`mandrill`](http://mandrill.com/), [`mailgun`](http://www.mailgun.com/), [`postmark`](https://postmarkapp.com/) and [`sendgrid`](http://sendgrid.com/)  
  Each service requires your own account and an API key.

`email_handler_key`
: If you are using an email service, your API key goes here.

`emails`
: This is an array that contains each email's settings. [More info](/docs/configuring/emails).

`discounts_folder`
: Location (from root) to find discounts  
  <small>`_content/discounts`</small>

`coupons_folder`
: Location (from root) to find coupons  
  <small>`_content/discounts`</small>
  
`create_members`
: Whether to create members at checkout. [More info](/docs/configuring/members)

`clear_customer_details`
: Whether or not to clear the customer's details from session at checkout  
  <small>`false`</small>

`control_panel`
: An array containing your control Panel specific options. [More info](/docs/configuring/control-panel)
