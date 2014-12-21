---
title: Members
---

You can create a member account upon checkout by setting the `create_members` config variable to `true` in `bison.yaml`.

In your checkout flow, you need to have a `username` and `password` fields.

It doesn't matter if you enter these fields in a customer info form or a checkout form. If they are missing, a member will not be created. 

Bison will only save fields to the member profile that you have allowed in the member bundle fields config. (`/_config/bundles/member/fields.yaml`)

Any custom data fields will have `custom_data` stripped off. So if you have `custom_data[phone_number]` in your checkout flow, it will be converted to `phone_number`. This means that if you want to add member registration fields into your checkout flow, you should use `custom_data[my_field]`. Keep in mind these will also get saved to the order entry. 

