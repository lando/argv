# ARGV

A very simple module called `argv` that allows you to:

* Check whether certain flags exist in `process.argv`
* Get the value of a flag in `process.argv`

## Installation

```bash
# With npm
npm install @lando/argv

# With yarn
yarn add @lando/argv
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

## Issues, Questions and Support

If you have a question or would like some community support we recommend you [join us on Slack](https://launchpass.com/devwithlando). Note that this is the Slack community for [Lando](https://lando.dev) but we are more than happy to help with this module as well!

If you'd like to report a bug or submit a feature request then please [use the issue queue](https://github.com/lando/argv/issues/new/choose) in this repo.

## Changelog

We try to log all changes big and small in both [THE CHANGELOG](https://github.com/lando/argv/blob/main/CHANGELOG.md) and the [release notes](https://github.com/lando/argv/releases).


## Development

* Requires [Node 14+](https://nodejs.org/dist/latest-v14.x/)
* Prefers [Yarn](https://classic.yarnpkg.com/lang/en/docs/install)

```bash
git clone https://github.com/lando/argv.git && cd argv
yarn install
```

If you dont' want to install Node 14 or Yarn for whatever reason you can install [Lando](https://docs.lando.dev/basics/installation.html) and use that:

```bash
git clone https://github.com/lando/argv.git && cd argv
# Install deps and get node
lando start

# Run commands
lando node
lando yarn
```

## Testing

```bash
# Lint the code
yarn lint

# Run unit tests
yarn test
```

## Releasing

```bash
yarn release
```

## Contributors

<a href="https://github.com/lando/argv/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=lando/argv" />
</a>

Made with [contributors-img](https://contrib.rocks).

## Other Resources

* [Important advice](https://www.youtube.com/watch?v=WA4iX5D9Z64)
