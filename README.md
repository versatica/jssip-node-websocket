## jssip-node-websocket

`JsSIP.Socket` interface for the Node.js based on the [websocket](https://www.npmjs.com/package/websocket) module.

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


### `var socket = new NodeWebSocket(url, origin, headers, requestOptions, clientConfig)`

* `url` (String): The WebSocket URL.
* `origin`, `headers`, `requestOptions` and `clientConfig` match the same meaning and format of the same parameters given to the [websocket.W3CWebSocket](https://github.com/theturtle32/WebSocket-Node/blob/08fc659153f9f77744b97e5db307278a580c105c/docs/W3CWebSocket.md) class constructor.


## Author

Iñaki Baz Castillo ([@ibc](https://github.com/ibc/) at Github)


## License

[ISC](./LICENSE)
