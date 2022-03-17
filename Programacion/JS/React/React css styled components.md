

Instalación

```bash
npm install styled-components 
```


Para el siguiente componente utilizaremos style components

```javascript 
import React from 'react'
import { Category } from '../Category'
import { List, Item } from './styles'

import cat from './db.json'

export const ListOfCategories = () => {
  return (
    <List>
      {
            cat.categories.map(category => <Item key={category.id}> <Category {...category} /> </Item>)
        }
    </List>
  )
}
```

Tenemos el style Component

 ```javascript
import styledComponents from 'styled-components'

export const List = styledComponents.ul`
    display: flex;
    overflow: scroll;
    width: 100%;
`

export const Item = styledComponents.li`
    padding: 0 8px;
`

 ```
De la parte más importnate es que cambiamos por ejemplo el tag de <li> por <Item> 

