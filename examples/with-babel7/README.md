
add Webpack as Dev dependency

```
npm install --save-dev webpack webpack-cli
```

add Babel as Dev dependency
```
npm install --save-dev babel-loader @babel/core @babel/preset-env html-webpack-plugin script-ext-html-webpack-plugin
```
- @babel/core — This is the engine that will pick up all the configuration provided to run plugins to transpile the latest version of JavaScript through syntax transformers into plain vanilla versions supported by the target platform. Notice that this uses@babel/ which means it is a scope package².
- @babel/preset-env — This scope package is a Babel preset that compiles code down to ES5 by automatically determining the Babel plugins and polyfills needed based on the targeted browser or runtime environments. By default it behaves exactly the same as babel-preset-latest (or babel-preset-es2015, babel-preset-es2016, and babel-preset-es2017 together)³ .
- babel-loader — This is the Babel plugin for Webpack, it will be added to the Webpack configuration to instruct it to run the target files though Babel during the bundling process. Note that it is not using scope packages.
- html-webpack-plugin — This is a Webpack plugin that allows as to bundle and process HTML files. It is not really required by the bare minimal setup but is helpful to get the HTML files into the distribution
- script-ext-html-webpack-plugin — This is a Webpack plugin which is not really required by the bare minimal setup as well. But it allows the automation of injecting the bundled javascript into the HTML files that is included in the distribution

```
npm install --save-dev @babel/register
```

@babel/register — This scope package provides the require hook that will bind itself to node’s require and automatically compile files on the fly for Babel. Webpack uses js-interpret⁵ internally to call register the package as a module to transpile the Webpack configuration file for execution. It requires the file to be named with a .babel.js suffix to work.