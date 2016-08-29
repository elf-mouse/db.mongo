__Q:__ DeprecationWarning: Mongoose: mpromise (mongoose's default promise library) is deprecated, plug in your own promise library instead: http://mongoosejs.com/docs/promises.html

__A:__ Plugging in your own Promises Library

```js
// Use native promises
mongoose.Promise = global.Promise;

// or Use bluebird
mongoose.Promise = require('bluebird');

// or Use q. Note that you **must** use `require('q').Promise`.
mongoose.Promise = require('q').Promise;
```
