---
title: Emails
---

Bison lets you send emails to your customers and administrators upon each successful order.  
You can use regular Statamic templates to create both HTML and plain text versions of your emails.

To set this up, you'll need to modify the values inside the `emails` array in `_config/add-ons/bison/bison.yaml`.

### Example
~~~
emails:
  disable_all: false
  order_complete_admin:
    enabled: true
    from: shop@mysite.com
    to: admin@mysite.com
    subject: An order has been submitted
    html_template: order_complete_admin
    text_template: order_complete_admin_text
  order_complete_customer:
    enabled: true
    from: shop@mysite.com
    subject: Thank you for your order
    html_template: order_complete_customer
    text_template: order_complete_customer_text
~~~

### Options

`disable_all`
: Acts as a master killswitch. If you want to disable all emails at once, set this to `true`.

`order_complete_admin`
:   Sent to an admin upon order completion.

    * `to` – Comma delimited list of email recipients.
    * `cc` – Same as `to`, but in the cc field.
    * `bcc` – Same as `to`, but in the bcc field.
    * `from` – The sender's email address.
    * `subject` – The subject line.
    * `html_template` – Template containing HTML version of the email.
    * `text_template` – Template containing text version of the email.

`order_complete_customer`
:   Sent to an customer upon order completion.

    * `from` – The sender's email address.
    * `subject` – The subject line.
    * `html_template` – Template containing HTML version of the email.
    * `text_template` – Template containing text version of the email.

### Templating
The templates that you supply to `html_template` and `text_template` are just regular Statamic templates. They should be stored in `_themes/theme_name/templates/`. You can nest them in subfolders for organization. You can use any tags. Any variables in the [order details](/docs/tags/checking-out#order_details) tag pair are available to you here.