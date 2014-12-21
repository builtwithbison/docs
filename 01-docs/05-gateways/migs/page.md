---
title: MIGS
tested: yes
intro: |
  Website: [mastercard.com](http://www.mastercard.com/us/company/en/whatwedo/payment_processing.html)
---

## 2-Party
Add the following to your `bison.yaml` file:
~~~
payment_gateway: Migs_TwoParty
gateway_settings:
  Migs_TwoParty:
    merchant_id:
    merchant_access_code:
    secure_hash:
~~~

## 3-Party
Add the following to your `bison.yaml` file:
~~~
payment_gateway: Migs_ThreeParty
gateway_settings:
  Migs_ThreeParty:
    merchant_id:
    merchant_access_code:
    secure_hash:
~~~