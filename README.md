AppCheck
======================

ApplicationCache updater based on the idea found at [html5rocks][2]

#### Usage

To enable the application cache for an app, include the manifest attribute on the document's html tag.

``````
<html manifest="example.appcache">
  ...
</html>
``````

A manifest file must be served with the mime-type text/cache-manifest.
You may need to add a custom file type to your web server or .htaccess configuration.

``````
AddType text/cache-manifest .appcache
``````

The manifest is a separate file you link to via the manifest attribute on the html element.

``````
CACHE MANIFEST
# 2010-06-18:v2

# Explicitly cached 'master entries'.
CACHE:
/favicon.ico
index.html
stylesheet.css
images/logo.png
scripts/main.js

# Resources that require the user to be online.
NETWORK:
*

# static.html will be served if main.py is inaccessible
# offline.jpg will be served in place of all images in images/large/
# offline.html will be served in place of all other .html files
FALLBACK:
/main.py /static.html
images/large/ images/offline.jpg
``````

Then include the appcheck javascript in your document to update the ApplicationCache.

``````
<script src="path/to/appcheck.js"></script>
``````

For more information about ApplicationCache visit: [html5rocks][2]

#### License

[GNU General Public License v2][3]

© 2014 - [ProtoMorph][1]

[1]: http://protomorph.cf/
[2]: http://www.html5rocks.com/en/tutorials/appcache/beginner/
[3]: http://opensource.org/licenses/GPL-2.0
