# Rewrite CSS Assets Webpack Plugin

A Webpack plugin to rewrite CSS assets.

## What does the plugin do?

It will search for CSS assets during the Webpack build and you can rewrite the CSS.

```
var CssRewritePlugin = require('css-rewrite-webpack-plugin');
module.exports = {
    module: {
        loaders: [
            { test: /\.css$/, loader: ExtractTextPlugin.extract("style-loader", "css-loader") }
        ]
    },
    plugins: [
        new ExtractTextPlugin("styles.css"),
        new distFontRewriterPlugin({
            fileReg: new RegExp('static/css/dist.css'),
            processor: function (source) {
                return source.replace(/static\/fonts/g, '..\/fonts')
            }
        })
    ]
}
```

## License

MIT