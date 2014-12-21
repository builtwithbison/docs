---
title: Installing and updating
---
## Installing

* Download and unzip the archive
* Copy the contents of `_add-ons` into `_add-ons`.  
(Bison comes with the core, and a few additional sub-addons like fieldtypes.)
* Copy the contents of `_config/add-ons/bison` into to `_config/add-ons/bison`
* Rename `_config/add-ons/bison/_bison.yaml` to `bison.yaml`.
* If you are using Statamic 1.7, **do not** enable `_http_cache_expires`.

## Configuration 

* Add the required [configuration settings](/docs/configuring).
* Set up your [shipping method](/docs/configuring/shipping)
* Add appropriate [routes](/docs/configuring/routes)
* Add your [payment gateway details](/docs/gateways)

## Updating

* Download and unzip the archive
* Back up your existing `_add-ons/bison_*` folders.
* Copy the contents of `_add-ons` to `_add-ons`.
* Check `_config/add-ons/bison/_bison.yaml` for any newly added settings.
* Consult the [changelog](/changelog) for any version specific instructions.