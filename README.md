winston-sentry
==============

Sentry transport for winston logger for node js
-----------------------------------------------

Follow this sample configuration to use:

```javascript
var winston = require('winston'),
    Mail = require('winston-mail').Mail,
    Sentry = require('winston-sentry');

var logger = new winston.Logger({
    transports: [
        new winston.transports.Console({level: 'silly'}),
        new Sentry({
                level: 'warn',
                dsn: "{{ YOUR SENTRY DSN }}"
        })
    ],
});
```

If you want to use patchGlobal to catch all uncaught errors, simply pass it as option like this:

```javascript
new Sentry({
    patchGlobal: true
});
```
    
Winston logging levels are mapped to the default sentry levels like this:

    silly: 'debug',
    verbose: 'debug',
    info: 'info',
    debug: 'debug',
    warn: 'warning',
    error: 'error',

    
