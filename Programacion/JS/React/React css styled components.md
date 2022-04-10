## Styled Components
Styled components enable the creation of React components with CSS styling. The styled components are intended to assist developers with:


* Creating unique class names for the styles we use is essentially the same as creating a component that we can use. Reduces the number of bugs caused by the use of class names.
* Simplified the maintenance of the styling code, making it easier to change or delete CSS.
* Automatically manage code splitting, resulting in a better user experience when our application is loaded.
* This method ensures that you will not have problems with CSS collitions if you define different styles in different components.

Styled Components requires the installation of the following packages.

```bash
npm install styled-components --save
```


It is critical to appoint this package is a production dependency. In the following example,

In this case, we'll be utilizing the Name.js component. This component should appear as follows:

```javascript 
import React from 'react'
import { Article } from '../UI/Article'
import {Comment, Submit} from './styles'

export const Name = () => {
  return (
    <Article >
        <h2>NAME</h2>
        <Comment >Insert the name to verify the gender</Comment>
        <form>
            <label htmlFor='gname'></label>
            <input type='text' id='gname' name='gname'></input>
            <Submit type='submit' value='check' />
        </form>
    </Article>
  )
}

```

And our styled component should appear as follows:

 ```javascript
import styledComponents from 'styled-components'

export const Comment = styledComponents.p`
    font-style: oblique;
    font-size: x-small;
    color: blue;
`

export const Submit = styledComponents.input`
    display: inline - block;
    margin: 0.5rem;
    color: gray;
    opacity: 0.7;
    font-style: italic;
    background - color: rgb(255, 255, 255);
    &:hover {
        opacity: 1;
        color: black;
        font-weight: bold;
        font-style: normal;
    }
`

 ```


### Conclusion about Styled components

If we create the project's run build with

```bash
npm run build
```

It is important to note that the css style is no longer used in the styled components, so the css style is included in the javascript file. We can see the'main.js' file and examine it.

![prev](./img/React-css-04.png)

Pay attention to the 'n' symbols now. It has all of the indentation that we used previously. And keep in mind that when we build something, we expect the output files to be optimized and minimal.

The advantages of this approach could be as follows:

* We use styled-components to create new components, which we then use in our custom components.
* Our components, on the other hand, are easier to read and maintain.
* The files are not optimized because they contain white spaces and symbols that are not required by the file.



## module.css versus Styled components 

To draw some conclusions, I constructed the project with styled components and module CSS, and the result is

![prev](./img/React-css-10.png)


The left image shows'module.css,' while the right image shows'styled components.'

It is important to note that when I create the project with the 'npx create-react-app' command, it generates a css global file that I do not delete. That is why the styled component project includes a css minimal file.

My current point of view is

* When comparing Javascript files, the'module.css' is smaller, despite the fact that the'styled components' is slower to load.
* The styles in'modules.css' are optimized and minimal. The styles from the'styled components' included in the main javascript are not optimized or minimal. As a result, the page loads slower with'styled components' than with'module.css'.
* In comparison to'module.css,"styled.components' is easier to maintain and prevents bugs due to the names of the classes.

As a result, I preferred to use'module.css'. It would be great if you could comment on which approach you prefer and why.

I hope this post has helped you better understand how to style your applications.

