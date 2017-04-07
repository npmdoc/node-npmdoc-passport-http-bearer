# api documentation for  [passport-http-bearer (v1.0.1)](https://github.com/jaredhanson/passport-http-bearer#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-passport-http-bearer.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-passport-http-bearer) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-passport-http-bearer.svg)](https://travis-ci.org/npmdoc/node-npmdoc-passport-http-bearer)
#### HTTP Bearer authentication strategy for Passport.

[![NPM](https://nodei.co/npm/passport-http-bearer.png?downloads=true)](https://www.npmjs.com/package/passport-http-bearer)

[![apidoc](https://npmdoc.github.io/node-npmdoc-passport-http-bearer/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-passport-http-bearer_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-passport-http-bearer/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-passport-http-bearer/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-passport-http-bearer/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jared Hanson",
        "email": "jaredhanson@gmail.com",
        "url": "http://www.jaredhanson.net/"
    },
    "bugs": {
        "url": "http://github.com/jaredhanson/passport-http-bearer/issues"
    },
    "dependencies": {
        "passport-strategy": "1.x.x"
    },
    "description": "HTTP Bearer authentication strategy for Passport.",
    "devDependencies": {
        "chai": "1.x.x",
        "chai-passport-strategy": "0.1.x",
        "mocha": "1.x.x"
    },
    "directories": {},
    "dist": {
        "shasum": "147469ea3669e2a84c6167ef99dbb77e1f0098a8",
        "tarball": "https://registry.npmjs.org/passport-http-bearer/-/passport-http-bearer-1.0.1.tgz"
    },
    "engines": {
        "node": ">= 0.4.0"
    },
    "homepage": "https://github.com/jaredhanson/passport-http-bearer#readme",
    "keywords": [
        "passport",
        "auth",
        "authn",
        "authentication",
        "authz",
        "authorization",
        "http",
        "bearer",
        "token",
        "oauth"
    ],
    "licenses": [
        {
            "type": "MIT",
            "url": "http://www.opensource.org/licenses/MIT"
        }
    ],
    "main": "./lib",
    "maintainers": [
        {
            "name": "jaredhanson",
            "email": "jaredhanson@gmail.com"
        }
    ],
    "name": "passport-http-bearer",
    "optionalDependencies": {},
    "readme": "# passport-http-bearer\n\n[![Build](https://travis-ci.org/jaredhanson/passport-http-bearer.png)](http://travis-ci.org/jaredhanson/passport-http-bearer)\n[![Coverage](https://coveralls.io/repos/jaredhanson/passport-http-bearer/badge.png)](https://coveralls.io/r/jaredhanson/passport-http-bearer)\n[![Dependencies](https://david-dm.org/jaredhanson/passport-http-bearer.png)](http://david-dm.org/jaredhanson/passport-http-bearer)\n\n\nHTTP Bearer authentication strategy for [Passport](http://passportjs.org/).\n\nThis module lets you authenticate HTTP requests using bearer tokens, as\nspecified by [RFC 6750](http://tools.ietf.org/html/rfc6750), in your Node.js\napplications.  Bearer tokens are typically used protect API endpoints, and are\noften issued using OAuth 2.0.\n\nBy plugging into Passport, bearer token support can be easily and unobtrusively\nintegrated into any application or framework that supports\n[Connect](http://www.senchalabs.org/connect/)-style middleware, including\n[Express](http://expressjs.com/).\n\n## Install\n\n    $ npm install passport-http-bearer\n\n## Usage\n\n#### Configure Strategy\n\nThe HTTP Bearer authentication strategy authenticates users using a bearer\ntoken.  The strategy requires a 'verify' callback, which accepts that\ncredential and calls 'done' providing a user.  Optional 'info' can be passed,\ntypically including associated scope, which will be set by Passport at\n'req.authInfo' to be used by later middleware for authorization and access\ncontrol.\n\n    passport.use(new BearerStrategy(\n      function(token, done) {\n        User.findOne({ token: token }, function (err, user) {\n          if (err) { return done(err); }\n          if (!user) { return done(null, false); }\n          return done(null, user, { scope: 'all' });\n        });\n      }\n    ));\n\n#### Authenticate Requests\n\nUse 'passport.authenticate()', specifying the ''bearer'' strategy, to\nauthenticate requests.  Requests containing bearer tokens do not require session\nsupport, so the 'session' option can be set to 'false'.\n\nFor example, as route middleware in an [Express](http://expressjs.com/)\napplication:\n\n    app.get('/profile', \n      passport.authenticate('bearer', { session: false }),\n      function(req, res) {\n        res.json(req.user);\n      });\n\n#### Issuing Tokens\n\nBearer tokens are typically issued using OAuth 2.0.  [OAuth2orize](https://github.com/jaredhanson/oauth2orize)\nis a toolkit for implementing OAuth 2.0 servers and issuing bearer tokens.  Once\nissued, this module can be used to authenticate tokens as described above.\n\n## Examples\n\nFor a complete, working example, refer to the [Bearer example](https://github.com/jaredhanson/passport-http-bearer/tree/master/examples/bearer).\n\n## Related Modules\n\n- [OAuth2orize](https://github.com/jaredhanson/oauth2orize) — OAuth 2.0 authorization server toolkit\n\n## Tests\n\n    $ npm install\n    $ npm test\n\n## Credits\n\n  - [Jared Hanson](http://github.com/jaredhanson)\n\n## License\n\n[The MIT License](http://opensource.org/licenses/MIT)\n\nCopyright (c) 2011-2013 Jared Hanson <[http://jaredhanson.net/](http://jaredhanson.net/)>\n",
    "readmeFilename": "README.md",
    "repository": {
        "type": "git",
        "url": "git://github.com/jaredhanson/passport-http-bearer.git"
    },
    "scripts": {
        "test": "node_modules/.bin/mocha --reporter spec --require test/bootstrap/node test/*.test.js"
    },
    "testling": {
        "browsers": [
            "chrome/latest"
        ],
        "harness": "mocha",
        "files": [
            "test/bootstrap/testling.js",
            "test/*.test.js"
        ]
    },
    "version": "1.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module passport-http-bearer](#apidoc.module.passport-http-bearer)
1.  [function <span class="apidocSignatureSpan">passport-http-bearer.</span>Strategy (options, verify)](#apidoc.element.passport-http-bearer.Strategy)
1.  [function <span class="apidocSignatureSpan">passport-http-bearer.</span>super_ ()](#apidoc.element.passport-http-bearer.super_)
1.  object <span class="apidocSignatureSpan">passport-http-bearer.</span>super_.prototype

#### [module passport-http-bearer.super_](#apidoc.module.passport-http-bearer.super_)
1.  [function <span class="apidocSignatureSpan">passport-http-bearer.</span>super_ ()](#apidoc.element.passport-http-bearer.super_.super_)
1.  [function <span class="apidocSignatureSpan">passport-http-bearer.super_.</span>Strategy ()](#apidoc.element.passport-http-bearer.super_.Strategy)

#### [module passport-http-bearer.super_.prototype](#apidoc.module.passport-http-bearer.super_.prototype)
1.  [function <span class="apidocSignatureSpan">passport-http-bearer.super_.prototype.</span>authenticate (req, options)](#apidoc.element.passport-http-bearer.super_.prototype.authenticate)



# <a name="apidoc.module.passport-http-bearer"></a>[module passport-http-bearer](#apidoc.module.passport-http-bearer)

#### <a name="apidoc.element.passport-http-bearer.Strategy"></a>[function <span class="apidocSignatureSpan">passport-http-bearer.</span>Strategy (options, verify)](#apidoc.element.passport-http-bearer.Strategy)
- description and source-code
```javascript
function Strategy(options, verify) {
  if (typeof options == 'function') {
    verify = options;
    options = {};
  }
  if (!verify) { throw new TypeError('HTTPBearerStrategy requires a verify callback'); }

  passport.Strategy.call(this);
  this.name = 'bearer';
  this._verify = verify;
  this._realm = options.realm || 'Users';
  if (options.scope) {
    this._scope = (Array.isArray(options.scope)) ? options.scope : [ options.scope ];
  }
  this._passReqToCallback = options.passReqToCallback;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.passport-http-bearer.super_"></a>[function <span class="apidocSignatureSpan">passport-http-bearer.</span>super_ ()](#apidoc.element.passport-http-bearer.super_)
- description and source-code
```javascript
function Strategy() {
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.passport-http-bearer.super_"></a>[module passport-http-bearer.super_](#apidoc.module.passport-http-bearer.super_)

#### <a name="apidoc.element.passport-http-bearer.super_.super_"></a>[function <span class="apidocSignatureSpan">passport-http-bearer.</span>super_ ()](#apidoc.element.passport-http-bearer.super_.super_)
- description and source-code
```javascript
function Strategy() {
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.passport-http-bearer.super_.Strategy"></a>[function <span class="apidocSignatureSpan">passport-http-bearer.super_.</span>Strategy ()](#apidoc.element.passport-http-bearer.super_.Strategy)
- description and source-code
```javascript
function Strategy() {
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.passport-http-bearer.super_.prototype"></a>[module passport-http-bearer.super_.prototype](#apidoc.module.passport-http-bearer.super_.prototype)

#### <a name="apidoc.element.passport-http-bearer.super_.prototype.authenticate"></a>[function <span class="apidocSignatureSpan">passport-http-bearer.super_.prototype.</span>authenticate (req, options)](#apidoc.element.passport-http-bearer.super_.prototype.authenticate)
- description and source-code
```javascript
authenticate = function (req, options) {
  throw new Error('Strategy#authenticate must be overridden by subclass');
}
```
- example usage
```shell
...
      return done(null, user, { scope: 'all' });
    });
  }
));

#### Authenticate Requests

Use 'passport.authenticate()', specifying the ''bearer'' strategy, to
authenticate requests.  Requests containing bearer tokens do not require session
support, so the 'session' option can be set to 'false'.

For example, as route middleware in an [Express](http://expressjs.com/)
application:

app.get('/profile',
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
