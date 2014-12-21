---
title: Sage Pay
intro: |
  Website: [sagepay.co.uk](http://www.sagepay.co.uk/)
---

## Sage Pay Server
Add the following to your `bison.yaml` file:
~~~
payment_gateway: SagePay_Server
gateway_settings:
  SagePay_Server:
    vendor:
    test_mode:
    simulator_mode:
~~~ 

## Sage Pay Direct
Add the following to your `bison.yaml` file:
~~~
payment_gateway: SagePay_Direct
gateway_settings:
  SagePay_Direct:
    vendor:
    test_mode:
    simulator_mode:
~~~ 