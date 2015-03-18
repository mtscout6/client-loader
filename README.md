# client-loader
Webpack loader to allow module to be defined separately for client and server.

## Usage

Add two modules to your project, both similar in purpose. However, target one
for the browser and the other for the server.

```
ScriptName.js
ScriptName.client.js
```

In the script that is dependant on that module require normally as
`require('ScriptName')`.

Add as final loader for your js, coffee, etc.

``` javascript

module.exports = {
  ...
  module: {
    loaders: [
      { test: /\.js$/, loader: 'client' }
    ]
  }
};
```

Webpack will bundle the `ScriptName.client.js` file and not the `ScriptName.js`
file.
