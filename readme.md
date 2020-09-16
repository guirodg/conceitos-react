# Primeiro comando para na nossa pasta

- yarn init -y
- Criar pasta src and public

# Terminal

- yarn add react react-dom _React para web react-dom_

# Ferramentas

- Babel: Converter codigo React para o browser
- Webpack: Cada tipo de arquivo (js,css,png) converte de uma forma diferente para poder importar js,css,png para meu javascript

- Loaders: css-loader, image-loader

## Adicionando Babel Webpack Loaders

- yarn add @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli

- criar arquivo babel.config.js

```
module.exports = {
    presets: [
        '@babel/preset-env',
        '@babel/preset-react'
    ],
};
```

- yarn add @babel/cli

## Webpack

- yarn add babel-loader

```
const path = require("path");

module.exports = {
  entry: path.resolve(__dirname, "src", "index.js"),
  output: {
    path: path.resolve(__dirname, "public"),
    filename: "bundle.js",
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exlude: /node_modules/,
        uuse: {
          loader: "babel-loader",
        },
      },
    ],
  },
};
```

- yarn webpack --mode development

## Comando para o webpack ficar observando atualizaçoes no codigo

- yarn add webpack-dev-server -D

```
devServer: {
    contentBase:path.resolve(__dirname, 'public'),
  },
```

- yarn webpack-dev-server --mode development

## Conceitos do React

- Componentes
- Propiedades

  - children _Acessa o conteudo do meu componete_

- Estado & Imutabilidade

# CSS instalar no webpack

- no aqv

```
      {
        test: /\.css$/,
        exclude: /node_modules/,
        use: [{ loader: "style-loader" }, { loader: "css-loader" }],
      },

      {
        test: /.*\.(gif|png|jpe?g)$/i,
        use: {
          loader: 'file-loader',
        }
      }

```

- yarn add style-loader css-loader
- yarn add file-loader _carregar aqv dentro da minha aplicacao_

## Conectando API no meu front

- yarn add axios
  _Logo em seguida criar folder services and file api.js_

  useEffect => Utilizado para toda vez que tiver alteração na minha função ele atualiza, ele recebe dois parametros qual funcao e quando

## plugins para babel entender async

yarn add @babel/plugin-transform-runtime -D

```
plugins: [
  '@babel/plugin-transform-runtime'
]
```
