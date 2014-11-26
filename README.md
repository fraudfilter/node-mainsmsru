# node-mainsmsru
NPM module for HTTP API of mainsms.ru


## usage example
```javascript
var mainsms = require('mainsmsru')(process.env.MAINSMS_API_KEY);
mainsms.message.send({
  test: 1,
  run_at: undefined,
  sender: 'sender-name',
  project: 'my-awesome-project',
  recipients: ['9261112233', '9161112233'],
  message: 'hello, world!',
}, function (err, res) {
  console.log('ERROR: ', err);
  console.log('RESULT: ', res);
});
```

## api description

I'll describe only the differences between this module and original docs.

All methods get `options` and `callback` input parameters: `function (options, callback) {...}`, where `callback` must be a function taking arguments `error` and `result`: `function (err, res) {...}`. If everything's fine than `err` will be equal `undefined`, otherwise it will contain an object `{ code: <numeric error code>, message: 'error description'}`.

You must provide your [API key](http://mainsms.ru/office/api_account) before using this module: `var mainsms = require('mainsmsru')('YOUR_API_KEY')`. In every following paragraph I suppose you named this module as `mainsms`;


### message

object: `mainsms.message`  
docs: http://mainsms.ru/home/mainapi

##### send
  + `recipients` parameter can be not only the string of comma delimited numbers (e.g. `'9110000000,9120000000'`), but also a number itself (e.g. `'9110000000'`) or an array of them (e.g. `['9110000000','9120000000']`).

##### status
  + not implemented

##### price
  + not implemented

##### balance
  + not implemented

##### info
  + not implemented

##### status
  + not implemented


### sending

object: `mainsms.sending`  
docs: http://mainsms.ru/home/sendingapi  
not implemented

### batch

object: `mainsms.batch`  
docs: http://mainsms.ru/home/batch  
not implemented

### group

object: `mainsms.group`  
docs: http://mainsms.ru/home/group_api  
not implemented

### contact

object: `mainsms.contact`  
docs: http://mainsms.ru/home/contact_api  
not implemented

### sender

object: `mainsms.sender`  
docs: http://mainsms.ru/home/sender_api  
not implemented
