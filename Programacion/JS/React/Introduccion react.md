# Introducción


To create a new proyect Para crear un proyecto se puede utilizar 

```bash
npx create-react-app prooyect 
```

Esto nos crea una estructura de proyecto. 


## Estructura propuesta

* APP
	* src
	* assets: 
		* components
			
			* Layout: header . .
			* UI: general UI elements
			* Other folders for the components

 **UI folder** los componentes se ven algo así 

 ```js
import React from 'react';
import classes from './Card.module.css';
const Card = ()=> {
     return (
            <div className={classes.card}>
                {props.children}
             </div>
            );
}
export default Card;
```


