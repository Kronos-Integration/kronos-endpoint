[![npm](https://img.shields.io/npm/v/kronos-endpoint.svg)](https://www.npmjs.com/package/kronos-endpoint)
[![Greenkeeper](https://badges.greenkeeper.io/Kronos-Integration/kronos-endpoint.svg)](https://greenkeeper.io/)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/Kronos-Integration/kronos-endpoint)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![Build Status](https://secure.travis-ci.org/Kronos-Integration/kronos-endpoint.png)](http://travis-ci.org/Kronos-Integration/kronos-endpoint)
[![bithound](https://www.bithound.io/github/Kronos-Integration/kronos-endpoint/badges/score.svg)](https://www.bithound.io/github/Kronos-Integration/kronos-endpoint)
[![codecov.io](http://codecov.io/github/Kronos-Integration/kronos-endpoint/coverage.svg?branch=master)](http://codecov.io/github/Kronos-Integration/kronos-endpoint?branch=master)
[![Coverage Status](https://coveralls.io/repos/Kronos-Integration/kronos-endpoint/badge.svg)](https://coveralls.io/r/Kronos-Integration/kronos-endpoint)
[![Known Vulnerabilities](https://snyk.io/test/github/Kronos-Integration/kronos-endpoint/badge.svg)](https://snyk.io/test/github/Kronos-Integration/kronos-endpoint)
[![GitHub Issues](https://img.shields.io/github/issues/Kronos-Integration/kronos-endpoint.svg?style=flat-square)](https://github.com/Kronos-Integration/kronos-endpoint/issues)
[![Stories in Ready](https://badge.waffle.io/Kronos-Integration/kronos-endpoint.svg?label=ready&title=Ready)](http://waffle.io/Kronos-Integration/kronos-endpoint)
[![Dependency Status](https://david-dm.org/Kronos-Integration/kronos-endpoint.svg)](https://david-dm.org/Kronos-Integration/kronos-endpoint)
[![devDependency Status](https://david-dm.org/Kronos-Integration/kronos-endpoint/dev-status.svg)](https://david-dm.org/Kronos-Integration/kronos-endpoint#info=devDependencies)
[![docs](http://inch-ci.org/github/Kronos-Integration/kronos-endpoint.svg?branch=master)](http://inch-ci.org/github/Kronos-Integration/kronos-endpoint)
[![XO code style](https://img.shields.io/badge/code_style-XO-5ed9c7.svg)](https://github.com/sindresorhus/xo)
[![downloads](http://img.shields.io/npm/dm/kronos-endpoint.svg?style=flat-square)](https://npmjs.org/package/kronos-endpoint)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

# kronos-endpoint

Named communication (end)-points inside of kronos

![request forwarding](doc/images/requestForwarding.png "Requests Forwading")

# API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [Endpoint](#endpoint)
    -   [direction](#direction)
    -   [opposite](#opposite)
-   [InterceptedEndpoint](#interceptedendpoint)
    -   [interceptors](#interceptors)
    -   [interceptors](#interceptors-1)
-   [ReceiveEndpoint](#receiveendpoint)
    -   [connected](#connected)
    -   [sender](#sender)
    -   [isOpen](#isopen)
    -   [receive](#receive)
    -   [isIn](#isin)
-   [SendEndpoint](#sendendpoint)

## Endpoint

**Parameters**

-   `name`  
-   `owner`  
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `options.opposite` **[Endpoint](#endpoint)** opposite endpoint
    -   `options.createOpposite` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** creates an opposite endpoint

### direction

Deliver data flow direction

Returns **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** delivers data flow direction 'in', 'out' or undefined

### opposite

Returns **[Endpoint](#endpoint)** representing the opposite direction

## InterceptedEndpoint

**Extends Endpoint**

Endpoint with a list of interceptors
also provides fistInterceptor and lastInterceptor

### interceptors

Returns **[Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;Interceptor>** the interceptors or empty array if none are present

### interceptors

Set the interceptors
a connected chain from array element 0 over all entries up to the last element
in the array is formed.
Additionally firstInterceptor and lastInterceptor are set.

**Parameters**

-   `newInterceptors` **[Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;Interceptor>** replaces all interceptors

## ReceiveEndpoint

**Extends InterceptedEndpoint**

Receiving Endpoint

**Parameters**

-   `name`  
-   `owner`  
-   `options`  

### connected

Connect other side to us

**Parameters**

-   `other` **[Endpoint](#endpoint)** endpoint to be connected to

### sender

Deliver the sending side Endpoint

Returns **[SendEndpoint](#sendendpoint)** the sending side

### isOpen

Are we able to receive requests

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if we are able to receive requests

### receive

If we know the sender we will inform him about our open/close state
by calling willBeClosed() and hasBeenOpened()

**Parameters**

-   `receive`   (optional, default `rejectingReceiver`)

### isIn

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## SendEndpoint

**Extends ConnectorMixin(InterceptedEndpoint)**

**Parameters**

-   `name`  
-   `owner`  
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `options.opposite` **[Endpoint](#endpoint)** 
    -   `options.hasBeenConnected` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** called after connected
    -   `options.hasBeenDisconected` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** called after disconnected
    -   `options.hasBeenOpened` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** called after receiver is open
    -   `options.willBeClosed` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** called before receiver is closed

# install

With [npm](http://npmjs.org) do:

```shell
npm install kronos-endpoint
```

# license

BSD-2-Clause
