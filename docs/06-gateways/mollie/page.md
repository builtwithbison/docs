---
title: Mollie
tested: yes
intro: |
  Website: [mollie.nl](https://www.mollie.nl/)
---

Add the following to your `bison.yaml` file:

~~~
payment_gateway: Mollie
gateway_settings:
  Mollie:
    apiKey:
~~~

You can enable test mode by using your test API key.