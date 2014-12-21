---
title: Dummy
tested: yes
special: yes
---

This gateway is useful for testing. You may like this when testing your checkout and you don't want to wait to connect to your gateway over and over.

Use the following card numbers when checking out:

* `4242424242424242` for a successful transaction.
* `4111111111111111` for a declined transaction.

To use it, simply add the following to your `bison.yaml` file:
~~~
payment_gateway: Dummy
~~~