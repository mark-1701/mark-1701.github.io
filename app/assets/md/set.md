# set

El objeto `Set` le permite almacenar valores únicos de cualquier tipo, ya sea valores primitivos o referencias a objetos.

```javascript
const mySet1 = new Set();

mySet1.add(1); // Set [ 1 ]
mySet1.add(5); // Set [ 1, 5 ]
mySet1.add(5); // Set [ 1, 5 ]
mySet1.add("algún texto"); // Set [ 1, 5, 'algún texto' ]
const o = { a: 1, b: 2 };
mySet1.add(o);

mySet1.add({ a: 1, b: 2 }); // o está haciendo referencia a un objeto diferente,
// por lo que está bien

mySet1.has(1); // true
mySet1.has(3); // false, ya que 3 no se ha agregado al conjunto
mySet1.has(5); // true
mySet1.has(Math.sqrt(25)); // true
mySet1.has("Algún Texto".toLowerCase()); // true
mySet1.has(o); // true

mySet1.size; // 5

mySet1.delete(5); // elimina 5 del conjunto
mySet1.has(5); // false, 5 ha sido eliminado

mySet1.size; // 4, ya que acabamos de eliminar un valor

console.log(mySet1);
// imprime en consola Set(4) [ 1, "algún texto", {…}, {…} ] en Firefox
// imprime en consola Set(4) { 1, "algún texto", {…}, {…} } en Chrome
```
## Iterando Set
```javascript
// iterar sobre los elementos en Set
// imprime en consola los elementos en el orden:
//   1, "algún texto", {"a": 1, "b": 2}, {"a": 1, "b": 2}
for (let item of mySet1) console.log(item)


// para acceder a los elementos tenemos que convertir el set en un map
// convertir el objeto Set en un objeto Array, con Array.from
const myArr = Array.from(mySet1) // [1, "algún texto", {"a": 1, "b": 2}, {"a": 1, "b": 2}]

```
