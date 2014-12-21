---
title: Gateways
_default_folder_template: docs
---

## Gateway Configuration

Bison makes use of the wonderful Omnipay library which comes bundled with a number of gateways.

Each gateway has slightly different settings to go into your [configuration file](/docs/configuring/settings). Each gateway's settings can be found on their respective pages. Also, depending on the gateway, you may need to add some JavaScript to your page.

In your configuration file, you need to specify the short name of the gateway to be used in `payment_gateway`, and the settings that it requires in `gateway_settings`.

For example: (take note of the casing of the gateway names)
~~~
payment_gateway: Stripe
gateway_settings:
  Stripe:
    api_key: myapikey
~~~

If you want to allow multiple gateways (perhaps you'd like your user to select between credit card or PayPal), you should specify the *default* gateway in `payment_gateway` and then the settings for all your gateways in `gateway_settings`.

~~~
payment_gateway: Stripe
gateway_settings:
  Stripe:
    api_key: myapikey
  Authorizenet_AIM:
    apiLoginId: myapikey
    transactionKey: mytransactionkey
    testMode: true
    developerMode: true
~~~

## Supported gateways
These gateways have been tested to work with Bison.

<ul class="supported-gateways">
{{ pages:listing folder="docs/gateways" conditions="tested:yes" sort_by="title" }}
  <li><a href="{{ url }}">{{ title }}</a></li>
{{ /pages:listing }}
</ul>

### Additional gateways
These gateways are included in Omnipay, the payment processing library Bison is built on, but have not been tested and verified in Bison itself. They may still work, though. If you have a need for these gateways, let us know and we'll try to work closely with you to squash any bugs that may pop up!

<ul class="untested-gateways">
{{ pages:listing folder="docs/gateways" conditions="tested:not yes" sort_by="title" }}
  <li><a href="{{ url }}">{{ title }}</a></li>
{{ /pages:listing }}
</ul>