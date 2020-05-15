[![npm](https://img.shields.io/npm/v/@kronos-integration/endpoint.svg)](https://www.npmjs.com/package/@kronos-integration/endpoint)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![minified size](https://badgen.net/bundlephobia/min/@kronos-integration/endpoint)](https://bundlephobia.com/result?p=@kronos-integration/endpoint)
[![downloads](http://img.shields.io/npm/dm/@kronos-integration/endpoint.svg?style=flat-square)](https://npmjs.org/package/@kronos-integration/endpoint)
[![GitHub Issues](https://img.shields.io/github/issues/Kronos-Integration/endpoint.svg?style=flat-square)](https://github.com/Kronos-Integration/endpoint/issues)
[![Build Action Status](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2FKronos-Integration%2Fendpoint%2Fbadge&style=flat)](https://actions-badge.atrox.dev/Kronos-Integration/endpoint/goto)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/Kronos-Integration/endpoint.git)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![Known Vulnerabilities](https://snyk.io/test/github/Kronos-Integration/endpoint/badge.svg)](https://snyk.io/test/github/Kronos-Integration/endpoint)
[![codecov.io](http://codecov.io/github/Kronos-Integration/endpoint/coverage.svg?branch=master)](http://codecov.io/github/Kronos-Integration/endpoint?branch=master)
[![Coverage Status](https://coveralls.io/repos/Kronos-Integration/endpoint/badge.svg)](https://coveralls.io/r/Kronos-Integration/endpoint)

# kronos-endpoint

Named communication (end)-points inside of kronos

![request forwarding](doc/images/requestForwarding.svg "Requests Forwading"){:height="310pt" width="325pt"}

# API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [isEndpoint](#isendpoint)
    -   [Parameters](#parameters)
-   [Endpoint](#endpoint)
    -   [Parameters](#parameters-1)
    -   [isDefault](#isdefault)
    -   [isDummy](#isdummy)
    -   [toStringAttributes](#tostringattributes)
    -   [isIn](#isin)
    -   [isOut](#isout)
    -   [direction](#direction)
    -   [jsonAttributes](#jsonattributes)
    -   [hasInterceptors](#hasinterceptors)
    -   [connectable](#connectable)
        -   [Parameters](#parameters-2)
    -   [hasConnections](#hasconnections)
    -   [isConnected](#isconnected)
        -   [Parameters](#parameters-3)
    -   [openConnection](#openconnection)
        -   [Parameters](#parameters-4)
    -   [closeConnection](#closeconnection)
        -   [Parameters](#parameters-5)
    -   [openConnections](#openconnections)
    -   [closeConnections](#closeconnections)
-   [ReceivableEndpoint](#receivableendpoint)
    -   [Parameters](#parameters-6)
    -   [isIn](#isin-1)
    -   [receive](#receive)
    -   [receive](#receive-1)
        -   [Parameters](#parameters-7)
-   [MultiConnectionEndpoint](#multiconnectionendpoint)
    -   [Parameters](#parameters-8)
    -   [getConnectionState](#getconnectionstate)
        -   [Parameters](#parameters-9)
    -   [setConnectionState](#setconnectionstate)
        -   [Parameters](#parameters-10)
    -   [isConnected](#isconnected-1)
        -   [Parameters](#parameters-11)
    -   [connections](#connections)
-   [SendEndpoint](#sendendpoint)
    -   [Parameters](#parameters-12)
    -   [isOut](#isout-1)
-   [ReceiveEndpoint](#receiveendpoint)
    -   [Parameters](#parameters-13)
    -   [isIn](#isin-2)
-   [DummyReceiveEndpoint](#dummyreceiveendpoint)
    -   [receive](#receive-2)
    -   [isIn](#isin-3)
    -   [isDummy](#isdummy-1)
-   [SendEndpointDefault](#sendendpointdefault)
    -   [isDefault](#isdefault-1)
-   [MultiSendEndpoint](#multisendendpoint)
    -   [Parameters](#parameters-14)
    -   [isOut](#isout-2)
-   [ReceiveEndpointDefault](#receiveendpointdefault)
    -   [isDefault](#isdefault-2)
-   [ReceiveEndpointSelfConnectedDefault](#receiveendpointselfconnecteddefault)

## isEndpoint

check for Endpoint

### Parameters

-   `object` **any** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if object is an Endpoint

## Endpoint

### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** endpoint name
-   `owner` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** of the endpoint (service)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `options.didConnect` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** called after receiver is present
    -   `options.interceptors` **(Interceptor | [Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)>)?** interceptors

### isDefault

Indicate whatever we are a default endpoint.
Default means buildin.

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** false

### isDummy

Indicate whatever we are a dummy endpoint.
Dummy endpoints are used duiring construction of the endpoint mesh.

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** false

### toStringAttributes

mapping of properties used in toString

Returns **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 

### isIn

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** false

### isOut

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** false

### direction

Deliver data flow direction

Returns **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** delivers data flow direction 'in', 'out', 'inout' or undefined

### jsonAttributes

additional attributes to present in json output

### hasInterceptors

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if there is at least one interceptor assigned

### connectable

Can we form a connection to the other side
in to out and out to in

#### Parameters

-   `other` **[Endpoint](#endpoint)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if we can be connected to the other endpoint

### hasConnections

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if there is at least one connection

### isConnected

Are we connected to a endpoint

#### Parameters

-   `other` **[Endpoint](#endpoint)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if there is a connection to the other endpoint

### openConnection

Actually start with the communication

#### Parameters

-   `other` **[Endpoint](#endpoint)** 
-   `backpointer` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if this is the call form back call from the other side

### closeConnection

Actually stop the communication

#### Parameters

-   `other` **[Endpoint](#endpoint)** 
-   `backpointer` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if this is the call form back call from the other side

### openConnections

opens all connections

### closeConnections

closes all connections

## ReceivableEndpoint

**Extends Endpoint**

### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** endpoint name
-   `owner` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** of the endpoint (service)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `options.receive` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** reciever function

### isIn

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** false

### receive

get the receive function

Returns **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** 

### receive

Set the receive function

#### Parameters

-   `receive` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** 

## MultiConnectionEndpoint

**Extends ReceivableEndpoint**

Multiple connection endpoint.
Can hold several connections.

### Parameters

-   `name`  
-   `owner`  
-   `options`   (optional, default `{}`)

### getConnectionState

Deliver connection state

#### Parameters

-   `other` **Entpoint** 

Returns **any** our state for the connection to other

### setConnectionState

Set connection state

#### Parameters

-   `other` **Entpoint** 
-   `state` **any** for the connection to other

### isConnected

Check connectivity

#### Parameters

-   `other` **[Endpoint](#endpoint)** 

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if we are connected with other

### connections

All connections

## SendEndpoint

**Extends ReceivableEndpoint**

Sending Endpoint.
Can only hold one connection.
Back connections to any further endpoints will not be established

### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** endpoint name
-   `owner` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** of the endpoint (service)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `options.connected` **[Endpoint](#endpoint)?** where te requests are delivered to
    -   `options.didConnect` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** called after receiver is present

### isOut

We are always _out_

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## ReceiveEndpoint

**Extends MultiConnectionEndpoint**

Receiving Endpoint.
Can receive from several endpoints.
By default a dummy rejecting receiver is assigned

### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** endpoint name
-   `owner` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** of the endpoint (service)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `options.receive` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** reciever function
    -   `options.connected` **[Endpoint](#endpoint)?** sending side

### isIn

We are always _in_

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## DummyReceiveEndpoint

**Extends Endpoint**

Dummy endpoints are used duiring construction of the endpoint mesh.

### receive

dummy does nothing by intention

### isIn

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true

### isDummy

Indicate whatever we are a dummy endpoint.
Dummy endpoints are used duiring construction of the endpoint mesh.

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true

## SendEndpointDefault

**Extends SendEndpoint**

Send Endpoint acting as a default endpoints

### isDefault

We are a default endpoint

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## MultiSendEndpoint

**Extends MultiConnectionEndpoint**

Multiple Sending Endpoint.
Can hold several connections.
Back connections to any further endpoints will not be established

### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** endpoint name
-   `owner` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** of the endpoint (service)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `options.connected` **[Endpoint](#endpoint)?** where te requests are delivered to
    -   `options.didConnect` **[Function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** called after receiver is present

### isOut

We are always _out_

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## ReceiveEndpointDefault

**Extends ReceiveEndpoint**

Receive Endpoint acting as a default endpoints

### isDefault

We are a default endpoint

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** always true

## ReceiveEndpointSelfConnectedDefault

**Extends ReceiveEndpointDefault**

Receiving endpoint wich can also send to itself

# install

With [npm](http://npmjs.org) do:

```shell
npm install kronos-endpoint
```

# license

BSD-2-Clause
