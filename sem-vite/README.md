```sh
# Configurando e instalando o  react
mkdir myapp
cd myapp
npm init -y
npm install react react-dom -D
npm install @babel/core @babel/cli @babel/preset-env @babel/preset-react babel-loader -D  # baixando o babel para desenvolvimento
```

```sh
mkdir src  # diretório de codigo base da aplicação
mkdir public  # diretório content arquivos publicos

touch babel.config.js  # arquivo de configuração do babel
touch public/index.html src/index.js
```

```js
// babel.config.js
module.exports = {
    presets: [
        "@babel/preset-env",
        ["@babel/preset-react", {"runtime": "automatic"}]
    ]
}
```sh
# instalação do webpack
npm install html-loader html-webpack-plugin webpack webpack-cli webpack-dev-server style-loader css-loader file-loader -D
```

```js
// webpack.config.js
const HtmlWebPackPlugin = require("html-webpack-plugin");

module.exports = {
    devtool: "source-map",
    entry: "./src/index.js",
    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /node_modules/,
                use: {loader: "babel-loader"}
            },
            {
                test: /\.html$/,
                use: [{loader: "html-loader"}]
            },
            {
                test: /\.css$/,
                use: ["style-loader", "css-loader"]
            },
            {
                test: /\.(png|jpe?g|gif)$/i,
                use: ["file-loader"]
            },
        ]
    },
    resolve: {
        extensions: [".js", ".jsx"],
    },
    plugin: new HtmlWebPackPlugin({
        template: "./public/index.html",
    }),
};
```
