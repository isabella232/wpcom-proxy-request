# This repository has moved!

It is now part of the [Calypso](https://github.com/Automattic/wp-calypso/tree/master/packages/wpcom-proxy-request) repository.

The published npm package will continue to be available as before, no changes necessary!

# wpcom-proxy-request

**Proxied cookie-authenticated REST-API and WP-API requests to WordPress.com**

You likely want to use the high-level APIs in [`wpcom.js`][wpcom.js]
instead of using this module directly.

This module offers access to the WordPress.com REST-API and WP-API via a proxying `<iframe>`
pointing to a special URL that proxies API requests on the host page's behalf.

It is intended to be used in the browser (client-side) via a bundler like
browserify or webpack.


### Installation

Install `wpcom-proxy-request` using `npm`:

``` bash
$ npm install wpcom-proxy-request
```

### Example

```es6
// Import wpcom-proxy-request handler
import proxy from 'wpcom-proxy-request';

proxy( '/me', function( err, body, headers ) {
  if (err) {
    throw err;
  }

  var div = document.createElement( 'div' );
  div.innerHTML = 'Your WordPress.com "username" is: <b>@' + res.username + '<\/b>';
  document.body.appendChild( div );
} );
```

### Running tests

Compile and `watch` client-test application
```cli
make watch-test-app
```

Run server
```
make run-test-app
```

Open a tab pointing to `http://calypso.localhost:3001/`

### License

MIT – Copyright Automattic 2014


[wpcom.js]: https://github.com/Automattic/wpcom.js
