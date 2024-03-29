# 220411 webpack

```shell
npm i -D webpack webpack-cli webpack-dev-server
```

webpack.config.js
```js
const path = require('path');

module.exports = {
  // 파일을 읽어들어기 시작하는 진입점(.js)
  entry: '',

  //결과물(번들)을 반환
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'main.js',
    clean: true
  }
}
```

```shell
npm i -D html-webpack-plugin
```

webpack.config.js
```js
const HtmlPlugin = require('html-webpack-plugin');

module.exports = {
  ...

  // 번들링 후 결과물의 처리 방식 등 다양한 플러그인들을 설정
  plugins: [
    new HtmlPlugin({
      template: './index.html'
    })
  ]
}
```

```shell
npm i -D copy-webpack-plugin
```

webpack.config.js
```js
const CopyPlugin = require('copy-webpack-plugin');

module.exports = {
  ...

  plugins: [
    ...
    new CopyPlugin({
      patterns: [
        { from: 'static' }
      ]
    })
  ]
}
```

```shell
npm i -D style-loader css-loader
```

webpack.config.js
```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          'style-lodaer',
          'css-loader'
        ]
      }
    ]
  }
}
```

