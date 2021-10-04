ARGV
==========

Lando's argv module allows you to:

* Check process.argv for the present of certain flags
* Set a default string value if the flag is present

Installation
------------

Usage
-----

This module has 2 functions ```hasOption``` and ```getOption```.

**hasOption**

Checks to see if a flag is present in process.argv.

```
const argv = require('argv');
argv.hasOption('--debug'));
```

**getOption**

Gets the flag string or flag boolean to pass to your processes.  It also allows you to set a default value if the flag is present and no string follows your flag.

```
const argv = require('argv');
argv.getOption('--debug', {defaultValue: '*'});
```

getOption will check for string variables such as:

```
hyperdrive list --debug "trill"
hyperdrive list --debug="trill"
```

Both commands will return the value trill.

Development
-----------

Testing
-------

* Linting via ```yarn lint```
* Unit tests via ```yarn test```

Releasing
---------

* ```yarn release```

Other Resources
---------------

* [Important advice](https://www.youtube.com/watch?v=WA4iX5D9Z64)
