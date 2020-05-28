### Webpack setup

```javascript
const path = require('path');
const webpack = require('webpack');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
	mode: 'development',
	entry: {
    'index': path.join(__dirname, 'app/index.ts')
  },
	output: {
		filename: '[name]-bundle.js',
		path: '/',
		devtoolLineToLine: true,
		pathinfo: true,
		sourceMapFilename: '[name].js.map'
	},
	devServer: {
		contentBase: path.join(__dirname, '/public'),
		port: 8080,
    compress: true
  },
	plugins: [
		new webpack.ProgressPlugin(), 
		new HtmlWebpackPlugin({
			template: './app/index.html',
			inject: 'body',
			title: 'testing',
			hash: true,
			minify: false
		})],

	module: {
		rules: [
			{
				test: /\.(html)$/,
				use: {
					loader: 'html-loader',
					options: {
					attrs: [':data-src']
					}
				}
			},
			{
        test: /\.tsx?$/,
        use: 'ts-loader',
        exclude: /node_modules/
      }
		]
	},
	resolve: {
		extensions: [".webpack.js", ".web.js", ".ts", ".tsx", ".js"]
	}
};
```