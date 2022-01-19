# Introducción CSS

Cascading style sheets

## cargar código css

Los códigos css deben cargarse al inicio del HTML, lo hacemos en el head 

```html
<head>
	<title>Document</title>
	<link href="main.css" type="text/css" rel="stylesheet" />
</head>
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



