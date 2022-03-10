# Jest

Librería para realizar test en Javascript

## Instalación 

Para la instalación se puede utilizar 

```bash
npm install jest --save-dev
```

Una vez instalado hay que configurar los scripts en el package.json

```json
{
	"scripts": {
	"test": "jest",
	"test:watch": "jest --watch"
	}
}
```

1. el script **jest** ejecuta todos las pruebas del proyecto
2. el script **jest --watch** se encarga de dejar jest revisando para cualquier cambio en los archivos para volver a realizar todos los tests. 

## Buenas prácticas

Una buena práctica es crear los tests dentro del directorio llamado

**__test__** 

El cual usualmente lo ponemos dentro del directorio src. 

Además los archivos usualmente siguen los nombres de la siguiente manera:

Para el archivo **index.js** creamos el archivo de test dentro de la carpeta de tests y lo nombramos **index.test.js**. 

## Ejecución de pruebas 

El siguiente comando ejecuta todas las pruebas dentro del proyecto

```bash
npm run test
```

Si queremos ejecutar pruebas de un archivo en especifico se puede ejecutar

```bash
npm run test ./src/__test__/index.test.js
```

Otra opción es 

```bash
npx jest ./src/__test__/index.test.js
```

## Reporte de la cobertura de pruebas en el código

Podemos pedirle a jest que analice el código y nos informe que partes del código no tienen test, para esto hacemos lo siguiente:

```bash
npx jest --coverage
```

jest con este comando crea un directorio llamado coverage, en el cual tiene un directorio interno llamado Icov-report, adentro tenemos el directorio index.html, el cual tiene el reporte de las funciones evaluadas. 

## Agrupar tests 

Para agrupar los tests con jest podemos hacer lo siguiente: 

```javascript
describe('Descripción de la agrupación de tests', () => {

	//Aca se escriben el conjunto de tests que se agrupan de acuerdo a criterios como funcionalidad, funciones o lo que sea necesario. 

});
```

## Tests

El siguiente ejemplo muestra un test sencillo el cual comprueba si una variable de texto contiene una palabra en especifico 

```javascript 
const text = "hola mundo";
  
test('Descripción específica del test', () => {
	expect(text).toMatch(/mundo/);
});
```

### Descripción de las comparaciones para los tests 

| expect(algo)       | descripción |
| ------------------ | ----------- |
| .toMatch()         |             |
| .toContain()       |             |
| .toBeGreaterThan() |             |
| .toBeTruthy()      |             |
| .toBe()            |             |


### Before y after tests
Para ejecutar configuraciones como setup generales para cada test o ejecutar un código antes de iniciar un conjunto de test podemos utilizar varias funciones. A continuación se muestra el uso de una función en específico:

```javascript
afterEach(()=>{
	//instrucciones que deben ejecutarse
});
```

También se puede utilizar 

| función    | descripción                               |
| ---------- | ----------------------------------------- |
| beforeAll  | Se ejecuta antes de todas las pruebas     |
| beforeEach | Se ejecuta antes de cada prueba           |
| afterAll   | Se ejecuta al finalizar todas las pruebas |
| afterEach  | Se ejecuta después de cada prueba         |

