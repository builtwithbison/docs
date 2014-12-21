---
title: PayPal
tested: yes
intro: |
  Website: [paypal.com](https://www.paypal.com/)
---

## PayPal Express
(Tested)  
Add the following to your `bison.yaml` file:
~~~
payment_gateway: PayPal_Express
gateway_settings:
  PayPal_Express:
    username:
    password:
    signature:
    test_mode:
    solution_type:
    landing_page:
    header_image_url:
~~~ 

## PayPal Pro
(Untested)  
Add the following to your `bison.yaml` file:
~~~
payment_gateway: PayPal_Pro
gateway_settings:
  PayPal_Pro:
    username:
    password:
    signature:
    test_mode:
~~~ 