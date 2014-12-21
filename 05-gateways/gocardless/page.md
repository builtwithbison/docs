---
title: GoCardless
tested: no
intro: |
  Website: [gocardless.com](https://gocardless.com/)
---

Add the following to your `bison.yaml` file:
~~~
payment_gateway: GoCardless
gateway_settings:
  GoCardless:
    app_id:
    app_secret:
    merchant_id:
    access_token:
    test_mode:
~~~