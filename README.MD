# Simple OSS

This is a local object storage tool written in Node.js. \
It allows you to store arbitrary serializable data in json format.

## Start

Install the dependencies.

```bash
npm install
```

And run build to generate two target library for ESModule and CommonJS Module.

```
npm run build
```

## Usage

import the module. This library offers two library for ESM and CommonJS module.

```javascript
import SimpleOSS from 'simple-oss';   // For ESM

var SimpleOSS = require('simple-oss') // For CommonJS module.
```

And then create an SimpleOSS instance.

```javascript
const OSS = SimpleOSS.createSimpleOSS('/path/to/storage');
```
The `path/to/storage` means that the storage directory for data. It stores serialized object data.

And next you can do operators such as `set`, `get` and `del`.

For example, to set an value.

```javascript
const value = { prop: 'data' }
OSS.set(value,'key-name')
```

And get the value for specified key. It will return `null` if the key does not exist.

```javascript
OSS.get('key-name') // { prop: 'data'}
OSS.get('other') // null
```

To delete the key-value.

```javascript
OSS.del('key-name')
```

To check if key-value pair exists

```javascript
OSS.exist('key-name') // false
```
