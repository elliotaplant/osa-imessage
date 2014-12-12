![osa-imessage](https://raw.githubusercontent.com/wtfaremyinitials/osa-imessage/master/resources/logowithtext.png)

osa-imessage
====

![](https://img.shields.io/npm/dm/osa-imessage.svg)
![](https://img.shields.io/npm/v/osa-imessage.svg)
![](https://img.shields.io/npm/l/osa-imessage.svg)

A node.js module to interact with iMessage.

Requires OSX 10.10 Yosemite.

Usage
====

###*Sending messages*

**Send a message to a phone number:**
```js
var messages = require('osa-imessage');

messages.send('Hello World!', '+15555555555', callback);
```

**Send a message to a contact:**
```js
var messages = require('osa-imessage');

messages.send('Hello World!', 'Johnny Appleseed', callback);
```

**Send a message to an iCloud account:**
```js
var messages = require('osa-imessage');

messages.send('Hello World!', 'john@icloud.com', callback);
```

###*Receiving messages*

```js
var messages = require('osa-imessage');

var messageEvents = messages.listen();

messageEvents.on('received', function(data){
    var message = data.text;           // "Hello, World!"
    var fromName = data.from.name;     // "Johnny Appleseed"
    var fromHandle = data.from.handle; // "john@icloud.com"
    var time = data.time;              //  Timestamp
});
```
