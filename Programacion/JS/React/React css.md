In this post we are going to study two different approaches to using styles in our applications. The two options that we present in this blog are "module.css" and "styled components". We are not going to discuss having CSS global. At the end of the post, we are going to have a conclusion about the two CSS approaches.

The application is very simple, and we anticipate it to look like this:

![prev](./img/React-css-01.png)

We will only use three components in this app: 'UI/Article.js,' 'Name/Name.js,' and 'Gender/Gender.js.'

![prev](./img/React-css-02.png)

The code will be available in the next release.

https://github.com/sierra-oe/Redux-ReactJS-Http-Request/releases/tag/v1.1


## module.CSS with react

This method allows you to create CSS files that will be applied only to the components into which you import them; the magic happens because when you build the project, it hashes the name in order to avoid repetition and overriting styles. It is critical to avoid bugs caused by the combination of component styles.

This approach is also too similar when writing HTML and CSS code, because you use classes to identify the elements you require.

If you are configuring your project step by step, you must follow the 'Installing dependencies' section; otherwise, you can skip ahead to 'Implementing module.css'.

### Installing dependencies

You don't need to install anything if you create your project with npx create react app. However, if you create your project step by step, as shown in the following link http://moroquin.shekalug.org/creating-a-reactjs-project-step-by-step/ , you will need to install:


```bash
npm install css-loader style-loader --save-dev
```

Now we need to add the rule to our webpack.config.js to tell them how to treat the CSS files that we use in our components.

```javascript 
{
	test: /\.css$/i,
	use: ['style-loader', 'css-loader'],
}
```

If you followed the previous post about creating a react app from scratch, your webpack.config.js file should look something like this.

```javascript 
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  mode: 'development',
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
      { test: /\.js$/, exclude: /node_modules/, use: { loader: 'babel-loader', options: { presets: ['@babel/preset-env', '@babel/preset-react'] } } },
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      }
    ]
  }
}
```


### Implementing module.css
It is important to note that for combention, the css files should be named 'ComponentName.module.css' with the'module' appended to the name, so in our component we are going to import


```javascript
	import classes from './Article.module.css'
```

Now we can use the class styles in our react component, as shown in the following code.

```JSX
	<article className={`${classes.main} ${props.className? props.className:''}`}     >
        {props.children}
    </article>
```


Our CSS class should look something like this:

```javascript
import React from 'react'
import classes from './Article.module.css'

export const Article = (props) => {
  return (
    <article className={`${classes.main} ${props.className? props.className:''}`}     >
        {props.children}
    </article>
  )
}
```

### Some conclutions about module.css

Now we can build the application to inspect the output a little more closely, which you can do by running:

```bash
npm run build
```

Now that we have a new folder called '/build,' we can search for the minimal CSS that should be in the 'build/static/css' folder, 

![prev](./img/React-css-03.png)

The image shows 

* All of the class names are hashed, and there are no issues with overriding styles in the code.
* The minified CSS file is optimal because it contains only the necessary white spaces, resulting in a small file size.





