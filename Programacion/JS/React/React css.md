# CSS with react

Para importarlo podemos 

```javascript
	import classes from './Header.module.css';
```

Debemos tener nuestro archivo css con una extensión .module.css. 

Y para utilizarlo en el JSX es de la siguiente manera:

```JSX
	<header className={classes.header}>
		...
	</header>
	<div className={classes['main-image']}>
		...
	</div>
```

