# Assets

### Overview

Assets refer to [static files](http://en.wikipedia.org/wiki/Static_web_page) (client side Javascript, CSS, images, etc) on your server that are accessible to the outside world. In Sails, these files are usually placed in the [`assets/`](http://beta.sailsjs.org/#/documentation/anatomy/myApp/assets) directory. When the server is lifted, a series of Grunt tasks, specified by the developer, processes the assets and copies them to a hidden temporary directory (`.tmp/public/`). The contents of this directory are what Sails serves when it recives an approprite request. It can be thought of as roughly equivalent to the "public" folder in [express](http://www.https://github.com/expressjs), or the "www" folder used by other web servers, like Apache. This convention allows Sails to perform automated tasks on these assets, like the compiling LESS, CoffeeScript, SASS and other intermidates, generating spritesheets, minifiyng and consolidating JS and CSS files, or just about anything you can do with a Grunt task.

### Static Middleware

Behind the scenes, Sails uses the [static middleware](http://www.senchalabs.org/connect/static.html) from Express to serve assets. You can configure this middleware (e.g. cache settings) in [`/config/http.js`](/#/documentation/reference/sails.config/sails.config.http.html).

##### `index.html`
Like most web servers, Sails follows the `index.html` convention. For instance, if you create the directory `assets/foo/`, and add the file `assets/foo/index.html`, it will be accessible at `http://example.com/foo`, as well as as att `http://example.com/foo/index.html`.

##### Precedence
It is important to note that the static [middleware](http://stephensugden.com/middleware_guide/) is installed **after** the Sails router. The result is that in a scenario where a [custom route](/#/documentation/concepts/Routes?q=custom-routes), and an asset file have the same path, the custom route will be called and will handle the request, without invoking the static file middlewere. For example, if you create the file `assets/index.html`, but also define the route `'/': 'PageController.index'` in [`config/routes.js`](/#/documentation/reference/sails.config/sails.config.routes.html), the PageController handler will be invoked instead of the `index.html` file.


<docmeta name="uniqueID" value="Assets220313">
<docmeta name="displayName" value="Assets">
