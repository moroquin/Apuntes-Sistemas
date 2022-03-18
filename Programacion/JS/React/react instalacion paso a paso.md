
in this post we are going to initiate a new react project step by step. The goal is to understand which dependencies we need and how they work together in the react world. 

## Dependencies 

To work with this mini how to tutorial you need to have installed NodeJs, 

## Initiating

We have to initiate a node project 

```bash
npm init
```

Now we have an empty project, so we have to create the first structure to our files, for that we have to create a src folder

```bash
mkdir src
```

Now we have to create our entry point, to that you have to create a file inside the source folder 

```bash
touch src/index.js
```


## Bundle the app

Now we have to think about to bundle all the future application. To achieve that we are goint to use webpack. 


```bash
npm install webpack webpack-cli --save-dev
```

Crear el archivo *webpack.config.js*

```javascript
	module.exports ={
		mode: "development",
		output: {
			filename: 'app.bundle.js'
		}
	}
```
 y agregamos en el *package.json* 

```json
{
	"scripts": {
		"test": "echo \"Error: no test specified\" && exit 1",
		"build": "webpack",
	}
}
```

Con esto tenemos webpack para compilar nuestro código

Ejecutar: 

```bash
npm run build
```

### webpack-html plugin
Para crearnos un html por defecto. 

Instalación

```bash 
npm install html-webpack-plugin --save-dev
```

configuramos el *webpack.config.js*

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin")

	module.exports ={
		mode: "development",
		output: {
			filename: 'app.bundle.js'
		},
		plugins:[
			new HtmlWebpackPlugin()
			]
		}
```

Y esto nos genera el html para devolver la respuesta

### webpack-dev-server

Para gener un servidor de desarrollo 

```bash
npm install webpack-dev-server --save-dev
```

despues configuramos el script en *package.json* y podemos ejecutar el servidor de desarrollo

```json
{
	"scripts": {
		"test": "echo \"Error: no test specified\" && exit 1",
		"build": "webpack",
		"dev": "webpack-dev-server"
	}
}
```

Ejecutar: 

```bash
npm run dev
```


### Instalación react react-dom

```bash
npm install react react-dom
```

### Primeros pasos con react

En el index.js agregamos el código 

```javascript
const react = require("react");
const reactDom = require("react-dom");

reactDom.render('Hola Mundo', document.body);
```

Si ejecutamos este código tendremos la aplicación funcionando. 

### Creación de nuestro html 
No es buena practica que webpackhtml nos genere el html, así que vamos a crear nuestro *index.html*

```html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id='app'></div>
</body>
</html>
```

Debemos de indicarle a webpack que no utilizara un html por defecto, sino que nosotros le diremos la plantilla, en el archivo *webpack.config.js*

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin")

module.exports ={
    mode: "development",
    output: {
        filename: 'app.bundle.js'
    },
    plugins:[
        new HtmlWebpackPlugin({
            template:'src/index.html'
        })
    ]
}
```

Y el id='app' nos va servir para renderizar nuestra aplicación, cambiamos el archivo *index.js* para decirle que utilizará el id app para que renderice nuestra aplicación

```javascript
const react = require("react");
const reactDom = require("react-dom");

reactDom.render('Hola Platzi!', document.getElementById('app'));
```

### Para utilizar jsx

*babe/preset-env* nos asegura que la transpilación sea por la última versión de java aceptada por el comité y no es una versión experimental

```bash
npm install @babel/core @babel/preset-env @babel/preset-react babel-loader --save-dev
```

Ahora cambiamos el archivo *webpack.config.js*

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin")

module.exports = {
    mode: "development",
    output: {
        filename: 'app.bundle.js'
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: 'src/index.html'
        })
    ],
    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /node_modules/,
                use: {
                    loader: 'babel-loader',
                    options: {
                        presets: ['@babel/preset-env', 
		                        '@babel/preset-react']
                    }
                }
            }
        ]
    }
}
```

y podemos modificar nuestro *index.js* para tener el siguiente output

```javascript 
const React = require("react");
const reactDom = require("react-dom");

reactDom.render(<h1>hola mundo</h1>, document.getElementById('app'));
```

Y listo estamos utilizando jsx

### React linter
Viene con reglas especificas para javascript tanto como para react

```bash 
npm install standard --save-dev
```

Añadimos un script al *package.json*

```json
{
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack",
    "dev": "webpack-dev-server",
    "lint": "standard"
  }
}
```

Ahora debemos ignorar algunos ficheros para no tener problemas con errores que no queremos manejar 

```json
{
  "standard":{
    "ignore": [
      "/api/**"
    ]
  }
}
```

Conectar lint con nuestro editor en el package.json

### Creando el App de nuestra aplicación 

Es una buena práctica crear un componente App para el entry point, primero creamos nuestro componente App.js. Podemos crearlo como un componente funcional: 

```javascript
import React from 'react'

export default function App () {
  return (
    <h1>hola mundo</h1>
  )
}
```

Una vez creado en nuestro index.js lo llamamos como un componente:

```javascript 
const React = require('react')
const reactDom = require('react-dom')
const { App } = require('./App')

reactDom.render(App, document.getElementById('app'))

``` 

### Componentes
para los componentes es buena práctica crear dentro de src una carpeta llamada components, y dentro crear carpetas para señalar el tipo de categoría. 



