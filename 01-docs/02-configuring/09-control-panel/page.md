---
title: Control Panel
---

As of Bison 1.3, you can view store related information through a specialized control panel area.

To enable it, you'll need to add `bison: true` to your `_admin_nav` setting in your `_config/settings.yaml` file. You should now see 'Store' in your CP nav bar.

![Control Panel](/assets/content/control-panel.jpg)

## Overview
The overview page shows some top level metrics and your 5 most recent orders.

## Products
You can see a list of products on this page. Make sure to specify the `product_folder` in your `bison.yaml`. If you have multiple product folders, they will all be combined.

You can also add new products from this page. If you have more than one product folder, the 'New Product' button will _not_ be visible.

The 'Price' column will display the value in your products' `price` field (or the appropriate field if you've changed the name).

You can specify the amount of products shown per paginated page by adding `products_per_page` to the `control_panel` array in `bison.yaml`.

## Orders
This section will allow you to view a list of your orders and view each of them as a nicely formatted order details page instead of the regular publish page. Details shown on the order page include billing and shipping details, items and totals, discounts used, members, custom_data, and gateway details.

You can specify the amount of orders shown per paginated page by adding `orders_per_page` to the `control_panel` array in `bison.yaml`.

It's recommended to hide your orders from the 'Content' section by adding the following to your order folder's `page.md`:

```
_admin:
  hide: yes
```

## Discounts
This section allows you to view and manage your discounts in a more customized listing view.

You may add new discounts from this page using the 'New Discount' button. If your coupons are saved to a separate folder from your discounts, you will also get a 'New Coupon' button.

It's recommended to hide your discounts from the 'Content' section by adding the following to your discount folder's `page.md`:

```
_admin:
  hide: yes
```

## Settings
This section allows you to view the more important settings as a troubleshooting mechanism.

You can also view your currently configured gateways as well as configuring new ones. By selecting 'All Gateways' you can view a list of all the available gateways Bison offers. Then you can expand a row to see the configuration YAML needed to add to your `bison.yaml`.