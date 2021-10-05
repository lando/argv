# ARGV

A very simple module called `argv` that allows you to:

* Check whether certain flags exist in `process.argv`
* Get the value of a flag in `process.argv`

## Installation

```bash
# With npm
npm install https://github.com/lando/argv.git#1.0.0

# With yarn
yarn add https://github.com/lando/argv.git#1.0.0
```

## Usage

This module has two functions `hasOption` and `getOption`.

### hasOption

Checks to see if a flag exists in `process.argv`.

```js
const argv = require('argv');

// Will return Boolean
const hasDebug = argv.hasOption('--debug'));
```

### getOption

Returns the value of the flag. If the flag is a switch then it will return `true|false` by default. If the flag has a `string` value it will return that string value.

```js
// File: myscript.js
const argv = require('argv');

console.log(argv.getOption('--debug'));
```

The above code will produce the following:

```bash
node myscript.js --debug
> true

node myscript.js --debug "trill"
> trill

hyperdrive list --debug=trill
> trill
```

You also can replace the default Boolean value with the `defaultValue` option.

```js
// File: myscript.js
const argv = require('argv');

console.log(argv.getOption('--debug', {defaultValue: 'the-truth-is-out-there'}));
```

```bash
node myscript.js --debug
> the-truth-is-out-there
```

## Development

* Requires Node 14+
* Prefers `yarn`

```bash
git clone https://github.com/lando/argv.git && cd argv
yarn install
```

## Testing

```bash
# Lint the code
yarn lint

# Run unit tests
# yarn test
```

## Releasing

```bash
yarn release
```

## Other Resources

* [Important advice](https://www.youtube.com/watch?v=WA4iX5D9Z64)
