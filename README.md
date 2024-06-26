@taktikorg/praesentium-ipsam-quis
----------------------

[![npm version](https://badge.fury.io/js/@taktikorg/praesentium-ipsam-quis.svg)](http://badge.fury.io/js/@taktikorg/praesentium-ipsam-quis)
[![dependencies](https://david-dm.org/balena-io-modules/@taktikorg/praesentium-ipsam-quis.png)](https://david-dm.org/balena-io-modules/@taktikorg/praesentium-ipsam-quis.png)
[![Build Status](https://travis-ci.org/balena-io-modules/@taktikorg/praesentium-ipsam-quis.svg?branch=master)](https://travis-ci.org/balena-io-modules/@taktikorg/praesentium-ipsam-quis)
[![Build status](https://ci.appveyor.com/api/projects/status/w9kqe2ok1rbkj42y?svg=true)](https://ci.appveyor.com/project/balena-io-modules/@taktikorg/praesentium-ipsam-quis)

Join our online chat at [![Gitter chat](https://badges.gitter.im/balena-io/chat.png)](https://gitter.im/balena-io/chat)

Balena settings storage utilities.

Role
----

The intention of this module is to provide low level access to how balena persists settings in both the filesystem and the browser.

**THIS MODULE IS LOW LEVEL AND IS NOT MEANT TO BE USED BY END USERS DIRECTLY**.

Unless you know what you're doing, use the [balena SDK](https://github.com/balena-io/balena-sdk) instead.

Installation
------------

Install `@taktikorg/praesentium-ipsam-quis` by running:

```sh
$ npm install --save @taktikorg/praesentium-ipsam-quis
```

Documentation
-------------


* [storage](#module_storage)
    * [.getStorage(options)](#module_storage.getStorage) ⇒ <code>storage</code>
        * [~set(name, value)](#module_storage.getStorage..set) ⇒ <code>Promise</code>
        * [~get(name)](#module_storage.getStorage..get) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;\*&gt;</code>
        * [~has(name)](#module_storage.getStorage..has) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;Boolean&gt;</code>
        * [~remove(name)](#module_storage.getStorage..remove) ⇒ <code>Promise</code>
        * [~clear()](#module_storage.getStorage..clear) ⇒ <code>Promise</code>

<a name="module_storage.getStorage"></a>

### storage.getStorage(options) ⇒ <code>storage</code>
**Kind**: static method of [<code>storage</code>](#module_storage)  
**Summary**: Get an instance of storage module  
**Access**: public  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>Object</code> | options |
| [options.dataDirectory] | <code>String</code> \| <code>False</code> | the directory to use for storage in Node.js or false to create an isolated in memory instance. Values other than false are ignored in the browser. |

**Example**  
```js
// with es6 imports
import { getStorage } from '@taktikorg/praesentium-ipsam-quis';
// or with node require
const { getStorage } = require('@taktikorg/praesentium-ipsam-quis');

const storage = getStorage({
	dataDirectory: '/opt/cache/balena'
});
```

* [.getStorage(options)](#module_storage.getStorage) ⇒ <code>storage</code>
    * [~set(name, value)](#module_storage.getStorage..set) ⇒ <code>Promise</code>
    * [~get(name)](#module_storage.getStorage..get) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;\*&gt;</code>
    * [~has(name)](#module_storage.getStorage..has) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;Boolean&gt;</code>
    * [~remove(name)](#module_storage.getStorage..remove) ⇒ <code>Promise</code>
    * [~clear()](#module_storage.getStorage..clear) ⇒ <code>Promise</code>

<a name="module_storage.getStorage..set"></a>

#### getStorage~set(name, value) ⇒ <code>Promise</code>
**Kind**: inner method of [<code>getStorage</code>](#module_storage.getStorage)  
**Summary**: Set a value  
**Access**: public  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>String</code> | name |
| value | <code>\*</code> | value |

**Example**  
```js
storage.set('token', '1234')
```
<a name="module_storage.getStorage..get"></a>

#### getStorage~get(name) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;\*&gt;</code>
**Kind**: inner method of [<code>getStorage</code>](#module_storage.getStorage)  
**Summary**: Get a value  
**Returns**: <code>[ &#x27;Promise&#x27; ].&lt;\*&gt;</code> - value or undefined  
**Access**: public  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>String</code> | name |

**Example**  
```js
storage.get('token').then((token) => {
	console.log(token)
});
```
<a name="module_storage.getStorage..has"></a>

#### getStorage~has(name) ⇒ <code>[ &#x27;Promise&#x27; ].&lt;Boolean&gt;</code>
**Kind**: inner method of [<code>getStorage</code>](#module_storage.getStorage)  
**Summary**: Check if the value exists  
**Returns**: <code>[ &#x27;Promise&#x27; ].&lt;Boolean&gt;</code> - has value  
**Access**: public  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>String</code> | name |

**Example**  
```js
storage.has('token').then((hasToken) => {
	if (hasToken) {
		console.log('Yes')
	} else {
		console.log('No')
});
```
<a name="module_storage.getStorage..remove"></a>

#### getStorage~remove(name) ⇒ <code>Promise</code>
**Kind**: inner method of [<code>getStorage</code>](#module_storage.getStorage)  
**Summary**: Remove a value  
**Access**: public  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>String</code> | name |

**Example**  
```js
storage.remove('token')
```
<a name="module_storage.getStorage..clear"></a>

#### getStorage~clear() ⇒ <code>Promise</code>
**Kind**: inner method of [<code>getStorage</code>](#module_storage.getStorage)  
**Summary**: Remove all values  
**Access**: public  
**Example**  
```js
storage.clear()
```

Support
-------

If you're having any problem, please [raise an issue](https://github.com/taktikorg/praesentium-ipsam-quis/issues/new) on GitHub and the balena team will be happy to help.

Tests
-----

Run the test suite by doing:

```sh
$ npm test
```

Contribute
----------

- Issue Tracker: [github.com/balena-io-modules/@taktikorg/praesentium-ipsam-quis/issues](https://github.com/taktikorg/praesentium-ipsam-quis/issues)
- Source Code: [github.com/balena-io-modules/@taktikorg/praesentium-ipsam-quis](https://github.com/taktikorg/praesentium-ipsam-quis)

Before submitting a PR, please make sure that you include tests, and that [coffeelint](http://www.coffeelint.org/) runs without any warning:

```sh
$ npm run lint
```

License
-------

The project is licensed under the Apache 2.0 license.
