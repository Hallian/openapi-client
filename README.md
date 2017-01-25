# OpenAPI Client

[![Greenkeeper badge](https://badges.greenkeeper.io/mikestead/openapi-client.svg)](https://greenkeeper.io/)

Generate ES6 or Typescript service integration code from an OpenAPI spec.

Also supports optional Redux action creator generation.

Tested against JSON services.

## Install

In your project

    npm install openapi-client --save-dev

Or globally to run CLI from anywhere

    npm install openapi-client -g

### Type Dependencies

If targeting TypeScript you'll also need to install the `isomorphic-fetch` typings in your project.

    npm install @types/isomorphic-fetch --save-dev

## Usage

### CLI

```
Usage: openapi [options]

Options:

  -h, --help              output usage information
  -V, --version           output the version number
  -s, --src <url|path>    The url or path to the Open API spec file
  -o, --outDir <dir>      The path to the directory where files should be generated
  -l, --language <js|ts>  The language of code to generate
  --redux                 True if wanting to generate redux action creators
```

### Code

```javascript
const openapi = require('openapi-client')
openapi.genCode({
  src: 'http://petstore.swagger.io/v2/swagger.json',
  outDir: './src/service',
  language: 'ts',
  redux: true
})
.then(complete, error)

function complete(spec) {
  console.info('Service generation complete')
}

function error(e) {
  console.error(e.toString())
}
```
