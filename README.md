# Webpack-loaders
Settings up loaders for webpack

# CSS loader

Using npm -- "npm install --save-dev css-loader"

Using Yarn -- "yarn add --dev css-loader"


# Babel loader (ES6)

Using npm -- "npm install --save-dev babel-loader babel-core babel-preset-env"

Using Yarn -- "yarn add --dev babel-loader babel-core babel-preset-env"

When installed open your webpack.config.js file and add new property "module" :

const path = require('path');

module.exports = {
  entry: {
    main: './src/main.js',
    about: './src/about.js',
  },
  output: {
    path: path.resolve('./dist'),
    filename: '[name].js'
  },
  module: {
    rules: [
    {
      test: /\.js$/,
      exclude: /node_modules/,
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['env']
        }
      }
    }
    ]
  }
};
