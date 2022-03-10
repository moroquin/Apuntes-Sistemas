# Introducción CSS

Cascading style sheets


## Style html

### Selectors

Use the same code for any selector
```html
	<head>
	...
		<style>
			section {
			background: red;
			}
		</style>
	</head>
	<body>
		...
		<section>
			<h1>Get the freedom you deserve</h1>
		</section>
		...
	</body>
```


## New file

Los códigos css deben cargarse al inicio del HTML, lo hacemos en el head 

```html
<head>
	<title>Document</title>
	<link href="main.css" type="text/css" rel="stylesheet" />
</head>
```

En el otro archivo

```css
section {
	background: red;
}
```

### Inline styling

*Not recomended*

```html
<section style="background: #d39026;">
	<h1>Get the freedom you deserve</h1>
</section>
```



## Selectores de css
Para aplicar las características del css lo podemos hacer seleccionando elementos dependiendo de nuestras necesidades. 

### Etiquetas de html 
Tienen el mismo nombre que su contraparte de html, el selector de *body* es *body*. 

Ejemplo:

```css
body{
	background-color: #fff;
}
```

### Por id

Esperamos tener un único ID en todo el html. 

html: 
```html
	<p id="parrafo">hola mundo </p>
```

css: 

```css
#parrafo {
	color: #fff;
	color:blue;
	font-family: Verdana;
}
```

### Por clase
Para darle un elemento a todos los elementos que compartan una clase

html: 
```html
	<p class="etiqueta">hola mundo </p>
```

css: 

```css
.etiqueta {
	color: #fff;
}
```


### Selector por atributo
Aplica a todos los elementos que tengan un atributo no importando quien sea
```html
<button disabled>
	Click
</button>
```

```css
[disabled] {
	color: red;
}
```

### Combinator
para combinar los selectores, que se encuentran dentro de otro id, y se puede usar aunque no sean hijos directos del elemento

```css
#product-overview h1{
	color: white;
}
```



### A todos los elementos 

Aplica a todos los elementos del html
```css
* {
	color:blue;
	font-family: Verdana;
}
```



## selectors, properties, values

| selectors   | properties       | values  |
| ----------- | ---------------- | ------- |
| div         | background-color | red     |
| .blog-post  | width            | 30%     |
| #main-title | color            | #fa923f |
| [disabled]  | margin           | 10px    |
| *           | display          | block   |






## Class selectors vrs id selectors

| css class selectors                                                       | CSS id selectors                                               |
| ------------------------------------------------------------------------- | -------------------------------------------------------------- |
| re utilizables, permite seleccionar items solo para propositos de estilos | conectada a un elemento en específico del html. Uno por página |
| Más utilizado                                                             | Solo si es necesario                                                               |



## !Important anotation

```css
div{
	color: red;
}
```

Sobre escribe las reglas anteriores. No es aconsejable. 
