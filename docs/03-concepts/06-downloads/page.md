Not all products are tangible. Sometimes you'll want to sell something downloadable, like 
software or ebooks. Bison can help you here too.

## Product field

First, add a field to your product that contains the path to the file for download. 

I'd suggest something like `/_downloads/my-product.zip` so you can keep everything organized, 
and protected.

```
download_path: "/_downloads/my-product.zip"
```

If you're using the control panel, just add a `file` field to your fieldset.

```
fields:
  download_path:
    type: file
    destination: _downloads/
    max_files: 1
```


## Protecting your files

You don't want people to be able to just type in the URL of your files to download them directly.

To protect the `_downloads` folder from being directly accessed, you should update your 
`.htaccess` file. You'll see a bunch of lines regarding protecting system files if you're
using the included htaccess from Statamic. Just add a line that points to your downloads folder.

```
# Protect your system files from prying eyes
RewriteRule ^(_app) - [F,L]
RewriteRule ^(_config) - [F,L]
RewriteRule ^(_content) - [F,L]
RewriteRule ^(_downloads) - [F,L]
```

Now if someone enters the URL of the file, they'll get a 403 forbidden error.


## Serving the file

To allow someone to download the file, there are a couple of tags to help you out.

You'll need to use `bison:file_download_link` to create a secure link, and `bison:download`
to read and process the download.

### Creating the download URL

First, create a template and a route that you'll use to trigger the downloads themselves. 

In `_config/routes.yaml`, you could create a `/download-file` URL.

``` yaml
routes:
  /download-file: download-file
```

This means whenever you visit `mysite.com/download-file`, it'll use the `download-file.html` 
template. In that file, you should add this:

```
{{ bison:download }}
```

That's it. What that does is read an encrypted path from the URL, and force a download of that
file. Your user will never even reach the `/download-file` page.

Now you'll need to create the encrypted link to this page.


### Creating an encrypted link

Once your user has checked out, you can create a download link for them. You could do this on
an order details page, or a dedicated download page. Whatever suits your project.

You can create this link using the [`bison:file_download_link`](/docs/tags/downloads/file_download_link)
tag.

```
{{ get_content from="/products/my-product" }}
  <a href="{{ bison:file_download_link url='/download-file' file='{ download_path }' member='{ current_member:username }' }}"
{{ /get_content }}
```

This will generate a link to the download route you created earlier, with an encrypted value tacked on
the end of it. By specifying the member, it'll create a link that only works if you are logged in as
that member, so it can't be shared.

