
# React router-dom

## install
```bash
npm install --save react-router-dom react-router
```

## Activate router 
Importan to wrap the App within BrowserRouter. 

```javascript
import ReactDOM from 'react-dom';
import { BrowserRouter } from 'react-router-dom';

import './index.css';
import App from './App';

import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(<BrowserRouter><App /></BrowserRouter>, document.getElementById('root'));
```


## Define routes


**Switch** it is used to stop when the route finds the first match. 

**exact** sirve para definir que la ruta debe ser exacta y no el primer match. 

**Redirect** sirve para redirecciónar una url cuando hace match

```javascript
import { Route, Switch, Redirect } from "react-router-dom";

function App() {

return (

	<Switch>
		<Route path='/' exact>
			<Redirect to='/quotes'/>
		</Route>
		
		<Route path='/quotes' exact>
			<AllQuotes/>
		</Route>
		
		<Route path='/quotes/:quoteId'>
			<QuoteDetails/>
		</Route>
		
		<Route path='/new-quotes'>
			<NewQuote/>
		</Route>
	</Switch>
	
	);

}

export default App;
```

## Extract params 

```javascript
import React from 'react';

import { useParams } from 'react-router-dom';

export default function QuoteDetails() {
	
	const params = useParams();
	
	return (
		<div>QuoteDetails{params.quoteId}</div>
		);
}
```



## Nested routes

Si necesitáramos una ruta dentro de otra para renderizar el componente comments

```javascript 
import React from 'react';
import { useParams, Route } from 'react-router-dom';
import { Fragment } from 'react/cjs/react.production.min';
import Comments from '../components/comments/Comments';

export default function QuoteDetails() {

const params = useParams();

return (
	<Fragment>
		<p>QuoteDetails{params.quoteId}</p>
		<Route path={`/quotes/${params.quoteId}/comments/`}>
			<Comments/>
		</Route>
	</Fragment>
	);
}
```

esta nested route también se pudo haber presentado de la siguiente manera:

```javascript
<Route path=`/quotes/:quoteId/comments/`></Route>
```

