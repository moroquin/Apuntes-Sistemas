# Combinators css

## Adjacent sibling
Elementos comparten el mismo padre, el segundo elemento debe venir inmediatamente. 
```css
h2 + p{
	color: red;
}
```

```html
<div>
	<h2>not applied</h2>
	<p>css applied</p>
	<h2>not applied</h2>
	<h3>not applied</h3>
	<p>not applied</p>
	<h2>not applied</h2>
	<p>css applied</p>
</div>
```
## combinators - general sibling

```css
h2 ~ p{
	color: red;
}
```

```html
<div>
	<h2>not applied</h2>
	<p>css applied</p>
	<p>css applied</p>
	<h2>not applied</h2>
	<h3>not applied</h3>
	<p>css applied</p>
	<h2>not applied</h2>
	<p>css applied</p>
</div>
```

## combinators - child

cualquier elemento que sea hijo directo 

```css
div > p{
	color: red;
}
```

```html
<div>
	<div>not applied</div>
	<p>css applied</p>
	<div>not applied</div>
	<article>
		<p>not applied</p>
	</article>
	<p>css applied</p>
</div>
```


## combinators - descendant

cualquier descendiente 

```css
div p{
	color: red;
}
```

```html
<div>
	<div>not applied</div>
	<p>css applied</p>
	<div>not applied</div>
	<article>
		<section>
			<p>css applied</p>
		</section>
	</article>
	<p>css applied</p>
</div>
```


