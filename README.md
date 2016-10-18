# Flux ES6 Cart App #

### Basic Setting ###

```
npm install flux react react-dom react-router@latest --save
npm install babel webpack webpack-dev-server -g
npm install babel-loader babel-preset-react babel-preset-es2015 --save-dev
```

```
mkdir dist
mkdir src
cd src
mkdir js
cd js
mkdir actions components constants dispatchers mixins stores
touch main.js
cd components
touch app.js
```

```
cd dist
touch index.html
```


##### webpack.config.js #####

```
module.exports = {
  entry: './src/js/main.js',
  output: {
    path: './dist',
    filename: "bundle.js",
    publicPath: '/'
  },
  devServer: {
    inline: true,
    contentBase: './dist'
  },
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        loader: 'babel',
        query: {
          presets: ['es2015', 'react']
        }
      }
    ]
  }
}
```

