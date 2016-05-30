## jssip-node-websocket

`JsSIP.Socket` interface for Node.js based on the [websocket](https://www.npmjs.com/package/websocket) module.

The aim of this module is to provide [JsSIP](http://jssip.net) with WebSocket support when running in Node.js.


## Installation

```bash
$ npm install jssip-node-websocket --save
```


## Requirements

* [jssip](http://jssip.net) >= `v2.0.0`
* Node.js >= `v4.0.0`


## Usage

```javascript
const JsSIP = require('jssip');
const NodeWebSocket = require('jssip-node-websocket');

let socket = new NodeWebSocket('wss://foo.example.com');

let ua = new JsSIP.UA(
  {
    uri          : 'sip:alice@example.com',
    password     : 'xxxxxxxx',
    display_name : 'Alice',
    sockets      : [ socket ]
  });
```


## API

The module exports a `NodeWebSocket` class conforming with the `JsSIP.Socket` interface.


### `var socket = new NodeWebSocket(url, [options])`

* `url` (String): The WebSocket URL.
* `options` (Object): An object with fields `origin`, `headers`, `requestOptions` and `clientConfig` matching the same meaning and format of the parameters given to the [websocket.W3CWebSocket](https://github.com/theturtle32/WebSocket-Node/blob/v1.0.23/docs/W3CWebSocket.md) class constructor.


## F.A.Q.

##### How to allow invalid TLS certificates?

```javascript
var socket = new Socket('wss://foo.example.com',
  {
    origin         : 'https://www.example.com',
    requestOptions :
    {
      agent : new https.Agent({ rejectUnauthorized: false })
    }
  });
```


## Author

Iñaki Baz Castillo ([@ibc](https://github.com/ibc/) at Github)


## License

[ISC](./LICENSE)
