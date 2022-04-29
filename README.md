# my_launchx_app

## Cómo crear un nuevo proyecto con JS paso a paso, agregando una clase y una prueba de unidad.

### Creando nuevo proyecto de JS.


Dentro del directorio donde se guardará el proyecto se ejecuta el comando `npm init.` Este ejecutará un cliente que te preguntará algunos datos de tu proyecto. Puedes darle enter hasta que termine. Al finalizar te creará el archivo `package.json.` En este preciso momento nuestro directorio es un proyecto de JS.
  

### Agregar dependencias nuevas al proyecto utilizando npm

Para agregar una dependencia, se necesita indicar directamente en el package.json. Para ello hacer uso de un comando de npm para agregar la última versión de cualquier dependencia: `npm install --save-dev jest.` Verificar que se haya creado un directorio `node_modules`, este contiene todos los scripts de js de las dependencias. 

NUNCA VERSIONAR ESTO. Para no versionar esta carpeta, crear en la RAÍZ del proyecto un archivo llamado `.gitignore` y agrega la siguiente línea: `**/node_modules` , con esto vamos a decirle a git que excluya este directorio.


### Exportar una clase e importarla en otro archivo para su uso.

[![](https://mermaid.ink/img/pako:eNpdjrEOwjAMRH8l8kq_ICswMnXNYjVusRQ7KHEGVPXfCbRduOl096S7FaYcCTxMCWu9MS4FJajr-iXuwbVy1msWQY1U9u4_dd5dRiusi1MUCrpjp2AAoSLIsS-t3y6APamD4LuNNGNLFiDo1tH2imh0j2y5gJ8xVRoAm-XxrRN4K41O6Dh8UNsHmNVE-w)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNpdjrEOwjAMRH8l8kq_ICswMnXNYjVusRQ7KHEGVPXfCbRduOl096S7FaYcCTxMCWu9MS4FJajr-iXuwbVy1msWQY1U9u4_dd5dRiusi1MUCrpjp2AAoSLIsS-t3y6APamD4LuNNGNLFiDo1tH2imh0j2y5gJ8xVRoAm-XxrRN4K41O6Dh8UNsHmNVE-w)

Crear la clase llamada MissionCommander, junto a un constructor que reciba un parámetro y lo agregue en el atributo name. Y al final exportar la clase:

~~~
class MissionCommander {
  constructor (name) {
    this.name = name
  }
}

// Esta línea nos permite exportar nuestra clase
module.exports = MissionCommander
~~~

### Cómo agregar una prueba de unidad básica con JEST.

Esta es una prueba básica de Jest:
~~~
describe("Esto es una suite de pruebas", () => {
  test('Caso de prueba 1', () => {
    const result = 1 + 2 
    expect(result).toBe(10);
  });
})
~~~
En el archivo package.json modificar la línea que inicia con "test" por:

`"test": "node ./node_modules/jest/bin/jest"`


