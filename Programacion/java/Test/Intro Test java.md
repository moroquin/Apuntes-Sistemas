# Intro Test java

Para utilizar tests podemos utilizar JUnint. Dependiendo como manejemos nuestro proyecto esto en maven lo podemos agregar en el pomXML. 

Los tests usualmente tienen la siguiente forma:
1. Preparación de los objetos
2. Ejecución del método 
3. Comprobación del resultado. 
## JUNIT
 es una librería que nos ayuda a facilitarnos la vida escribiendo tests, en este caso podemos utilizar las siguientes anotaciones:

 * Before: Se ejecuta antes de cada test, y básicamente nos sirve para definir el setup general para todos los tests. Parte importante es que si utilizamos esta notación, siempre se ejecuta al inicio de cada test. 
 * BeforeClass: se ejecuta una única vez, cuando necesitamos instanciar una única vez un objeto.  Debe ser statico
 * AfterClass: se ejecuta al finalizar la clase. Este debe ser statico. 
 * Test: identifica todos los tests que vamos ejecutar. 
 * After: se ejecuta al finalizar el test de la clase







