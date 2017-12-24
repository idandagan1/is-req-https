# isHttps
This module returns whether a request is under https

## Installation
```bash
npm i isHttps -S
```

## Users
 - Node.js
 - Express
 - Hapi
 
## Usage
If one of the following test is true, the function immediately return true.
- Check if `req.connection.encrypted` exist.
- Check the property `req.secure`.
- Check the `x-forwarded-proto` in headers
- Check `req.server.info.protocol` for Hapi requests

Otherwise the function returns false.

## Examples
```js
  const isHttps = require('isHttps');
  // for express users
  app.use((req, res, next) => {
    req.isSecure = isHttps(req);
});
``
