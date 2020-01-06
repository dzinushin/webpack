# webpack

Concepts

webpack is bundler

entry file

```
npx webpack [entry-file.js]
```
by default create  dist/main.js

configuration file ```webpack.config.js```


```
module.exports = {
  entry: __dirname + "/app/src/page.js",
  output: {
    path: __dirname + "/dist/",
  },
  optimization: {
    minimize: false
  },
}
```