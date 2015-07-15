---
title: Stripe
tested: yes
intro: |
  Website: [stripe.com](https://stripe.com/)
---

Add the following to your `bison.yaml` file:
~~~
payment_gateway: Stripe
gateway_settings:
  Stripe:
    api_key:
~~~

`api_key` refers to your *secret* key.

Instead of using regular payment fields in your checkout form, you will need to rename them and add Javascript according to the [Stripe docs](https://stripe.com/docs/stripe.js).

The token injected with Javascript should have a `name` attribute of `token`.

In order for your customers' billing details to appear in the Stripe dashboard with the order, make sure you are passing them along when generating a token using Stripe.js.
