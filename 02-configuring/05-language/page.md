---
title: Language
---
Bison includes a language file that is used to hold phrases such as the names of fields.

For example, this is how Bison knows whether to call the `cvv` field a 'CVV', 'CVC', 'CCV', 'Card Security Number' or 'that number on the back of your card'.

If you want to modify the wording or field names, you can use your own custom language file by renaming `_config/add-ons/bison/_custom_lang.yaml` to `custom_lang.yaml`. This will make sure your custom language file won't get overridden if/when you update Bison.