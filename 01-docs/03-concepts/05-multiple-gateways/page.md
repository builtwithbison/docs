---
title: Using Multiple Gateways
---
{{ noparse }}

If you want to give your customers the opportunity to check out with – for example – the choice of either a credit card or PayPal, you can do that!

## Settings
Add multiple gateway settings to your bison.yaml file and set a default.

~~~
payment_gateway: Stripe  # This will be the default
gateway_settings:
  Stripe:
    ...
  PayPal_Express:
    ...
~~~

## Templates
All of the gateways that are in the `gateway_settings` above will be available to you in an encrypted format using the [gateways](/docs/tags/checking-out/gateways) tag.

In your checkout_form, you are able to give the user the option to choose the gateway with a `gateway` field. For security, the value of this field needs to be encrypted - so we'll use the `gateways` tag.

~~~
{{ bison:checkout_form }}
  Gateway:
  <select name="gateway">
  {{ bison:gateways }}
    <option value="{{ value }}">{{ label }}</option>
  {{ /bison:gateways }}
  </select>
  <input type="submit" />
{{ /bison:checkout_form }}
~~~

## Differences in Gateways

Some gateways require different fields than others.  
For example:

* PayPal Express doesn't require credit card details from your site since your customer does all of that on the PayPal side.
* Stripe requires fields without `name` attributes, but needs `data-stripe` attributes instead, and also needs some JavaScript.
* If you want to process an order without accepting money you can use the Manual gateway - in which case you might want to capture extra data like phone numbers.

Nothing is stopping you from creating separate checkout pages for each gateway you require.
For example, on your payment page - which might default to credit card fields for Stripe - you might want to link to a separate page for offline payments using the 'Manual' gateway.

On that page, you can have another checkout_form, but you can specify the gateway as a parameter.

~~~
{{ bison:checkout_form gateway="Manual" }}
  Phone number: <input type="custom_data[phone]" />
  <input type="submit" />
{{ /bison:checkout_form }}
~~~

The gateway used in the transaction will be saved to the order entry.

Another option is to use the `gateways` tag to output some options, then use JavaScript to toggle different checkout forms. You're in control.

{{ /noparse }}