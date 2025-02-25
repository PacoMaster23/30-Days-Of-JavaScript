<div align="center">
  <h1> 30 Días De JavaScript: Función De Orden Superior</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Autor:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Enero, 2020</small>
</sub>

</div>

[<< Día 8](../dia_08_Objetos/dia_08_objetos.md) | [Día 10 >>](../dia_10_Sets_y_Maps/dia_10_sets_y_maps.md)

![Day 5](../images/banners/day_1_9.png)

- [Día 9](#día-9)
  - [Función De Orden Superior](#función-de-orden-superior)
    - [Callback](#callback)
    - [Retornar una función](#retornar-una-función)
    - [Configuración de tiempo](#configuración-de-tiempo)
      - [Configuración del intervalo mediante la función setInterval](#configuración-del-intervalo-mediante-la-función-setinterval)
      - [Configurar tiempo mediante un setTimeout](#configurar-tiempo-mediante-un-settimeout)
  - [Programación funcional](#programación-funcional)
    - [forEach](#foreach)
    - [map](#map)
    - [filter](#filter)
    - [reduce](#reduce)
    - [every](#every)
    - [find](#find)
    - [findIndex](#findindex)
    - [some](#some)
    - [sort](#sort)
      - [Ordenar los valores strings](#ordenar-los-valores-strings)
      - [Ordenar valores numéricos](#ordenar-valores-numéricos)
      - [Ordenar arrays de objetos](#ordenar-arrays-de-objetos)
  - [💻 Ejercicios](#💻-ejercicios)
    - [Ejercicios: Nivel 1](#ejercicios-nivel-1)
    - [Ejercicios: Nivel 2](#ejercicios-nivel-2)
    - [Ejercicios: Nivel 3](#ejercicios-nivel-3)

# Día 9

## Función De Orden Superior

Las funciones de orden superior son funciones que toman otra función como parámetro o retorna una función como valor. La función que se pasa como parámetro se llama callback.

### Callback

Un callback es una función que puede ser pasada como parámetro a otra función. Véase el ejemplo siguiente.

```js
// una función callback, el nombre de la función puede ser cualquier nombre
const callback = (n) => {
  return n ** 2
}
​
// función que toma otra función como callback
function cube(callback, n) {
  return callback(n) * n
}
​
console.log(cube(callback, 3))
```

### Retornar una función

Las funciones de orden superior retorna la función como valor
​

```js
// Función de orden superior que devuelve otra función
const higherOrder = (n) => {
  const doSomething = (m) => {
    const doWhatEver = (t) => {
      return 2 * n + 3 * m + t;
    };
    return doWhatEver;
  };
  return doSomething;
};
console.log(higherOrder(2)(3)(10));
```

Veamos dónde utilizamos las funciones de callback. Por ejemplo, el método _forEach_ utiliza callback.

```js
const numbers = [1, 2, 3, 4, 5];
const sumArray = (arr) => {
  let sum = 0;
  const callback = function (element) {
    sum += element;
  };
  arr.forEach(callback);
  return sum;
};
console.log(sumArray(numbers));
```

```sh
15
```

El ejemplo anterior puede simplificarse como el siguiente:

```js
const numbers = [1, 2, 3, 4]
​
const sumArray = arr => {
  let sum = 0
  arr.forEach(function(element) {
    sum += element
  })
  return sum

}
console.log(sumArray(numbers))
```

```sh
15
```

### Configuración de tiempo

En JavaScript podemos ejecutar algunas actividades en un determinado intervalo de tiempo o podemos programar (esperar) algún tiempo para ejecutar algunas actividades.

- setInterval
- setTimeout

#### Configuración del intervalo mediante la función setInterval

En JavaScript, utilizamos la función de orden superior setInterval para realizar alguna actividad de forma continua en un intervalo de tiempo determinado. El método global setInterval toma una función callback y una duración como parámetro. La duración está en milisegundos y la llamada de retorno siempre será llamada en ese intervalo de tiempo.

```js
// sintaxis
function callback() {
  // el código va aquí
}
setInterval(callback, duration);
```

```js
function sayHello() {
  console.log("Hello");
}
setInterval(sayHello, 1000); // imprime hola cada segundo, 1000ms es 1s
```

#### Configurar tiempo mediante un setTimeout

En JavaScript, utilizamos la función de orden superior setTimeout para ejecutar alguna acción en algún momento en el futuro. El método global setTimeout toma una función callback y una duración como parámetro. La duración está en milisegundos y el callback espera esa cantidad de tiempo.

```js
// sintaxis
function callback() {
  // el código va aquí
}
setTimeout(callback, duration); // duración en milliseconds
```

```js
function sayHello() {
  console.log("Hello");
}
setTimeout(sayHello, 2000); // imprime hola después de esperar 2 segundos.
```

## Programación funcional

En lugar de escribir un bucle regular, la última versión de JavaScript introdujo un montón de métodos incorporados que pueden ayudarnos a resolver problemas complicados. Todos los métodos incorporados toman la función callback. En esta sección, veremos _forEach_, _map_, _filter_, _reduce_, _find_, _every_, _some_, y _sort_.

### forEach

_forEach_: Iterar los elementos de un array. Utilizamos _forEach_ sólo con arrays. Toma una función callback con elementos, parámetro de índice y el propio array. El índice y el array son opcionales.

```js
arr.forEach(function (element, index, arr) {
  console.log(index, element, arr);
});
// El código anterior puede escribirse utilizando la función de flecha
arr.forEach((element, index, arr) => {
  console.log(index, element, arr);
});
// El código anterior puede escribirse utilizando la función de flecha y return explícito
arr.forEach((element, index, arr) => console.log(index, element, arr));
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num) => console.log(num));
console.log(sum);
```

```sh
1
2
3
4
5
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num) => (sum += num));

console.log(sum);
```

```sh
15
```

```js
const countries = ["Finland", "Denmark", "Sweden", "Norway", "Iceland"];
countries.forEach((element) => console.log(element.toUpperCase()));
```

```sh
FINLAND
DENMARK
SWEDEN
NORWAY
ICELAND
```

### map

_map_: Iterar los elementos de un array y modificar los elementos del mismo. Toma una función callback con elementos, índice , parámetro del array y devuelve un nuevo array.

```js
const modifiedArray = arr.map(function (element, index, arr) {
  return element;
});
```

```js
/*Función flecha y return explícito
const modifiedArray = arr.map((element,index) => element);
*/
//Ejemplo
const numbers = [1, 2, 3, 4, 5];
const numbersSquare = numbers.map((num) => num * num);

console.log(numbersSquare);
```

```sh
[1, 4, 9, 16, 25]
```

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const namesToUpperCase = names.map((name) => name.toUpperCase());
console.log(namesToUpperCase);
```

```sh
['ASABENEH', 'MATHIAS', 'ELIAS', 'BROOK']
```

```js
const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "Ireland",
  "Japan",
  "Kenya",
];
const countriesToUpperCase = countries.map((country) => country.toUpperCase());
console.log(countriesToUpperCase);

/*
// Función flecha
const countriesToUpperCase = countries.map((country) => {
  return country.toUpperCase();
})
//Función flecha de return explícita
const countriesToUpperCase = countries.map(country => country.toUpperCase());
*/
```

```sh
['ALBANIA', 'BOLIVIA', 'CANADA', 'DENMARK', 'ETHIOPIA', 'FINLAND', 'GERMANY', 'HUNGARY', 'IRELAND', 'JAPAN', 'KENYA']
```

```js
const countriesFirstThreeLetters = countries.map((country) =>
  country.toUpperCase().slice(0, 3)
);
```

```sh
 ["ALB", "BOL", "CAN", "DEN", "ETH", "FIN", "GER", "HUN", "IRE", "JAP", "KEN"]
```

### filter

_Filter_: Filtra los elementos que cumplen las condiciones de filtrado y devuelve un nuevo array.

```js
//Filtrar los países que contienen land
const countriesContainingLand = countries.filter((country) =>
  country.includes("land")
);
console.log(countriesContainingLand);
```

```sh
['Finland', 'Ireland']
```

```js
const countriesEndsByia = countries.filter((country) => country.endsWith("ia"));
console.log(countriesEndsByia);
```

```sh
['Albania', 'Bolivia','Ethiopia']
```

```js
const countriesHaveFiveLetters = countries.filter(
  (country) => country.length === 5
);
console.log(countriesHaveFiveLetters);
```

```sh
['Japan', 'Kenya']
```

```js
const scores = [
  { name: "Asabeneh", score: 95 },
  { name: "Lidiya", score: 98 },
  { name: "Mathias", score: 80 },
  { name: "Elias", score: 50 },
  { name: "Martha", score: 85 },
  { name: "John", score: 100 },
];

const scoresGreaterEighty = scores.filter((score) => score.score > 80);
console.log(scoresGreaterEighty);
```

```sh
[{name: 'Asabeneh', score: 95}, { name: 'Lidiya', score: 98 },{name: 'Martha', score: 85},{name: 'John', score: 100}]
```

### reduce

_reduce_: Reduce toma una función callback. La función callback toma como parámetro el acumulador, el valor actual y opcional el valor inicial y retorna un único valor. Es una buena práctica definir un valor inicial para el valor del acumulador. Si no especificamos este parámetro, por defecto el acumulador obtendrá el `primer valor` del array. Si nuestro array es un _array vacío_, entonces `Javascript` lanzará un error.

```js
arr.reduce((acc, cur) => {
  // algunas operaciones van aquí antes de devolver un valor
  return;
}, initialValue);
```

```js
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, cur) => acc + cur, 0);

console.log(sum);
```

```js
15;
```

### every

_every_: Comprueba si todos los elementos son similares en un aspecto. Devuelve un booleano

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const areAllStr = names.every((name) => typeof name === "string"); // ¿Son todas strings?

console.log(areAllStr);
```

```sh
true
```

```js
const bools = [true, true, true, true];
const areAllTrue = bools.every((b) => b === true); // ¿Son todas true?

console.log(areAllTrue); // true
```

```sh
true

```

### find

_find_: Retorna el primer elemento que cumple la condición

```js
const ages = [24, 22, 25, 32, 35, 18];
const age = ages.find((age) => age < 20);

console.log(age);
```

```js
18;
```

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const result = names.find((name) => name.length > 7);
console.log(result);
```

```sh
Asabeneh
```

```js
const scores = [
  { name: "Asabeneh", score: 95 },
  { name: "Mathias", score: 80 },
  { name: "Elias", score: 50 },
  { name: "Martha", score: 85 },
  { name: "John", score: 100 },
];

const score = scores.find((user) => user.score > 80);
console.log(score);
```

```sh
{ name: "Asabeneh", score: 95 }
```

### findIndex

_findIndex_: Retorna la posición del primer elemento que cumple la condición

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const ages = [24, 22, 25, 32, 35, 18];

const result = names.findIndex((name) => name.length > 7);
console.log(result); // 0

const age = ages.findIndex((age) => age < 20);
console.log(age); // 5
```

### some

_some_: Comprueba si algunos de los elementos son similares en un aspecto. Retorna un booleano

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const bools = [true, true, true, true];

const areSomeTrue = bools.some((b) => b === true);

console.log(areSomeTrue); //true
```

```js
const areAllStr = names.some((name) => typeof name === "number"); // ¿Son todas strings ?
console.log(areAllStr); // false
```

### sort

_sort_: El método "sort" ordena los elementos del array de forma ascendente o descendente. Por defecto, el método **_sort()_** ordena los valores como strings. Esto funciona bien para los elementos del array de strings pero no para los números. Si los valores numéricos se ordenan como strings y nos da un resultado erróneo. El método de Sort modifica el array original. Se recomienda copiar los datos originales antes de empezar a utilizar el método _sort_.

#### Ordenar los valores strings

```js
const products = ["Milk", "Coffee", "Sugar", "Honey", "Apple", "Carrot"];
console.log(products.sort()); // ['Apple', 'Carrot', 'Coffee', 'Honey', 'Milk', 'Sugar']
//Ahora la matriz original de productos también está ordenada
```

#### Ordenar valores numéricos

Como puede ver en el ejemplo de abajo, el 100 fue el primero después de ser clasificado en orden ascendente. Ordenar convierte los elementos en string , ya que '100' y otros números comparados, 1 que el principio del string '100' se convirtió en el más pequeño. Para evitar esto, utilizamos una función de callback de comparación dentro del método sort, que devuelve un negativo, un cero o un positivo.

```js
const numbers = [9.81, 3.14, 100, 37];
// El uso del método sort para ordenar los elementos numéricos proporciona un resultado erróneo.
console.log(numbers.sort()); //[100, 3.14, 37, 9.81]
numbers.sort(function (a, b) {
  return a - b;
});

console.log(numbers); // [3.14, 9.81, 37, 100]

numbers.sort(function (a, b) {
  return b - a;
});
console.log(numbers); //[100, 37, 9.81, 3.14]
```

#### Ordenar arrays de objetos

Siempre que ordenamos objetos en un array, utilizamos la clave del objeto para comparar. Veamos el siguiente ejemplo.

```js
objArr.sort(function (a, b) {
  if (a.key < b.key) return -1;
  if (a.key > b.key) return 1;
  return 0;
});

// o

objArr.sort(function (a, b) {
  if (a["key"] < b["key"]) return -1;
  if (a["key"] > b["key"]) return 1;
  return 0;
});

const users = [
  { name: "Asabeneh", age: 150 },
  { name: "Brook", age: 50 },
  { name: "Eyob", age: 100 },
  { name: "Elias", age: 22 },
];
users.sort((a, b) => {
  if (a.age < b.age) return -1;
  if (a.age > b.age) return 1;
  return 0;
});
console.log(users); // ordenados de forma ascendente
// [{…}, {…}, {…}, {…}]
```

🌕 Lo estás haciendo muy bien. Nunca te rindas porque las grandes cosas llevan su tiempo. Acabas de completar el día 9 de desafíos y llevas nueve pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y para tus músculos.

## 💻 Ejercicios

### Ejercicios: Nivel 1

```js
const countries = ["Finland", "Sweden", "Denmark", "Norway", "IceLand"];
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const products = [
  { product: "banana", price: 3 },
  { product: "mango", price: 6 },
  { product: "potato", price: " " },
  { product: "avocado", price: 8 },
  { product: "coffee", price: 10 },
  { product: "tea", price: "" },
];
```

1. Explique la diferencia entre **_forEach, map, filter, and reduce_**.
forEach: es para iterar los elementos de un array pero no devuelve un array.
map: es para iterar los elementos de un array y tambien modifica y devuelve los nuevos elementos del mismo.
filter: es para filtrar los elementos que cumplan las condiciones de filtrado y todo lo devuelve en un nuevo array.
  reduce: Acumula los valores del array en un solo resultado. Se le puede pasar un valor inicial como segundo argumento.

2. Defina una función callback antes de utilizarla en forEach, map, filter o reduce.
    arr.forEach ((element, index, arr) => {
      console.log("Elemento:",element)
      console.log("Indice:", index)
      console.log("Array:", arr)
    });

    const arrNew = arr.map((element, index) => {
      console.log("Mapeando el elemento:", element, "en la posicion:", index );

      return element;
    })

    const arrayNew = arr.filter(nuevo => nuevo.includes ("land"));
    o con varias lineas

    const arrayNew = arr.filter ((nuevo) => {
      if(nuevo.inlcudes("land")){
        console.log("Estos son los paises que tienen la palabra land",nuevo);
        return true;
      }else{
        return false;
      }
    })

3. Utiliza **_forEach_** para mostrar con console.log cada país del array de países.
        const countries = ["Mexico","Guatemala","Peru","Argentina"]
      countries.forEach((pais, index) =>{
         console.log(`${index +1}. ${pais}`);
      });
4. Utiliza **_forEach_** para mostrar con console.log cada nombre del array de nombres.
    nombres.forEach((nombre) => {
       console.log(`${nombre}`)
    })
    nombres.forEach(nombre => console.log(nombre));

5. Utiliza **_forEach_** para mostrar con console.log cada número del array de números.
  const numeros = [1,2,3,4,5,6,4]
  console.log("Lista de numeros")
  numeros.forEach(numero => console.log(numero))
6. Utiliza **_map_** para crear un nuevo array cambiando cada país a mayúsculas en el array de países.
  const newArray = countries.map(pais => pais.toUpperCase())
  console.log(newArray)
7. Utilice **_map_** para crear un array de longitudes de países a partir del array de países.
  const longiTud = countries.map(pais => pais.length)
  console.long(longiTud);
8. Usa **_map_** para crear un nuevo array cambiando cada número al cuadrado en el array de números.
  const numeros = [1,2,3,4,5,6,7,8,]
    const cuadradoNumero = numeros.map(numero => numero * numero)
    console.log(cuadradoNumero)
9. Utilice **_map_** para cambiar cada nombre a mayúsculas en el array de nombres.
    const nombres = ["Araceli","Paco","Cecilio","Angel"]
    const nombreMayus = nombres.map(nombre => nombre.toUpperCase());
    console.log(nombreMayus)
10. Utilice **_map_** para asignar el array de productos a sus correspondientes precios.
    const productos = [
      {producto: "Pepsi", precio: 23 },
      {producto:"Papas", precio: 34}
    ]
    const asignarPrecio = productos.map(producto =>  producto.precio)
    console.log(asignarPrecio )
11. Utilice **_filter_** para filtrar los países que contienen **_land_**.

    const paisSinLand = countries.filter(pais => pais.includes("land"));
    console.log(paisSinLand)
12. Utilice **_filter_** para filtrar los países que tienen seis caracteres.
    const seisCaracteres = countries.filter(pais => pais.length === 6)
     console.log(seisCaracteres)
13. Utilice **_filter_** para filtrar los países que contengan seis letras o más en el array de países.
  const masDeSeis = countries.filter(pais => pais.length >=6)
  console.log(masDeSeis)
14. Utilice **_filter_** para filtrar los países que empiezan por "E";
  const startConE = countries.filter(pais => pais.startsWith ("E"))
  console.log(startConE)
15. Utilice **_filter_** para filtrar sólo los precios con valores.
      const productos = [
      {producto: "Pepsi", precio: 23 },
      {producto:"Papas", precio: 34}
    ]
    const conValores =  productos.filter(producto => !isNaN(producto.precio))

16. Declara una función llamada getStringLists que toma un array como parámetro y devuelve un array sólo con elementos string.

  const getStringLists = (array)  => {
    return array.filter(item => typeof item === "string")
  };
17. Usa **_reduce_** para sumar todos los números del array de números.
  const numeros = [1,2,3,4,5,6]
    const sumaNumeros = numeros.reduce(acc, cur => acc + cur , 0)
    console.log(sumaNumeros)
18. Utiliza **_reduce_** para concatenar todos los países y producir esta frase: **_Estonia, Finland, Sweden, Denmark, Norway, y IceLand son países del norte de Europa_**
  
  const concat = countries.reduce((acc,pais, index, array) => {
    if(index !== array.length -1){
    return acc + pais + ', ';
    }
    return acc  + 'y ' + pais + 'son paises del norte de Europa';
    }, '');

19. Explique la diferencia entre **_some_** y **_every_**
every comprueba si todos los elemtnos son similares en un aspecto y  devuelve un booleano.
some: Comprueba si alguno de los elementos son similiares en un aspecto y si si retorna un booleano.
20. Utilice **_some_** para comprobar si la longitud de algunos nombres es superior a siete en el array de nombres.
const superior = nombres.some (nombre => nombre.length > 7);
21. Utilice **_every_** para comprobar si todos los países contienen la palabra land.
  const tieneLand = countries.every(pais => pais.includes("land"))
22. Explique la diferencia entre **_find_** y **_findIndex_**.
  find retorna el primer elememto que cumpla con la condicion dada.
  findIndex retorna la primer posicion del primer elemento que cumpla con la condicion dada.
23. Utilice **_find_** para encontrar el primer país que contenga sólo seis letras en el array de países.
  const seisLetras = countries.find(pais => pais.length === 6)
24. Utilice **_findIndex_** para encontrar la posición del primer país que contenga sólo seis letras en el array de países.
    const seisLetras = countries.findIndex(pais => pais.length === 6)
25. Utilice **_findIndex_** para encontrar la posición de **_Norway_** si no existe en el array obtendrá -1.
  const estaNor = countries.findIndex(pais => pais ==="Norway")
26. Utilice **_find_** para encontrar la posición de **_Russia_** si no existe en el array obtendrá -1.
  const estaNor = countries.find(pais => pais ==="Russia")


### Ejercicios: Nivel 2

1. Encuentre el precio total de los productos encadenando dos o más iteradores de matrices (por ejemplo, arr.map(callback).filter(callback).reduce(callback)).

const precios = arr.
filter(item => item.precio > 0 )
.map(item => item.precio)
.reduce((acc,item) => acc + item.precio,0)
      console.log(precios)

1. Encuentre la suma del precio de los productos usando sólo reduce(callback).

    const precioProductos = productos.reduce((acc,producto) => acc + producto.precio, 0)
    console.log(precioProductos)

1. Declara una función llamada **_categorizeCountries_** que retorna un array de países que tienen algún patrón común (encuentras el array de países en este repositorio como countries.js(ej 'land', 'ia', 'island','stan')).
    ESTA ES UNA FUNCION SOLO PARA DETECTAR UNA PALABRA
    const categorizarPaises = countries.filter(pais => pais.includes ("land"))
    console.log(categorizarPaises)
    
    PERO ESTA ES PARA ENCONTRAR VARIAS PALABRAS A LA VEZ

    function categorizarPais (patterns){
      return counties.filter(pais =>
        patterns.some(pattern => pais.includes(pattern))
      );
    }
    const patronesDeBusqueda = ["land","ia","island"]
    const categorizarPaiiis = categorizarPais(patrones);
    console.log(categorizarPais)

1. Cree una función que retorne un array de objetos, que es la letra y el número de veces que la letra usa para empezar el nombre de un país.


1. Declara una función **_getFirstTenCountries_** y retorna un array de diez países. Utiliza diferente programación funcional para trabajar en el array countries.js.
  //Usa slice para obtener los primeros elementos de un array de manera eficiente.
  function primeroDiez (){
    return countries.slice(0,10);
  }
  OTRA MANERA MAS COMPLEJA
    function diezPais (){
      return counties.filter(pais => pais.length === 10).slice(0,10);
    }
1. Declara una función **_getLastTenCountries_** que devuelve los últimos diez países del array de países.
  //MANERA FACIL
  function ultimosDiez (){
    return countries.slice(-10);
  }
  //MANERA CON MAS METODOS
  function almenosDiez (){
    return countries.length >=10 ? countries.slice(-10) : countries;
  }
1. Encuentre qué _letra_ se utiliza muchas _veces_ como inicial de un nombre de país del array de países (ej. Finland, Fiji, France etc)

  const empiezaCon = countries.filter(pais => pais.startsWith ('F'))

### Ejercicios: Nivel 3

1. Utiliza la información de los países, en la carpeta de datos. Ordena los países por nombre, por capital, por población
1. \*\*\* Encuentre las 10 lenguas más habladas:

   ````js
   // El resultado debería ser el siguiente
   console.log(mostSpokenLanguages(countries, 10))
   [
   {country: 'English',count:91},
   {country: 'French',count:45},
   {country: 'Arabic',count:25},
   {country: 'Spanish',count:24},
   {country:'Russian',count:9},
   {country:'Portuguese', count:9},
   {country:'Dutch',count:8},
   {country:'German',count:7},
   {country:'Chinese',count:5},
   {country:'Swahili',count:4}
   ]

   // El resultado debería ser el siguiente
   console.log(mostSpokenLanguages(countries, 3))
   [
   {country: 'English',count: 91},
   {country: 'French',count: 45},
   {country: 'Arabic',count: 25},
   ]```

    const primerosDiez = countries.sort((a,b) => a.name.localeCompare (b.name));
    const primerosNombres = countries.sort((a,b) => a.capital.localeCompare (b.capital));
    const primeraPoblacion = countires.sort((a,b) => a.population - b.population)
   ````

1. \*\*\* Utilice el archivo countries_data.js para crear una función que cree los diez países más poblados.

   ````js
   console.log(mostPopulatedCountries(countries, 10))

   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000},
   {country: 'Indonesia', population: 258705000},
   {country: 'Brazil', population: 206135893},
   {country: 'Pakistan', population: 194125062},
   {country: 'Nigeria', population: 186988000},
   {country: 'Bangladesh', population: 161006790},
   {country: 'Russian Federation', population: 146599183},
   {country: 'Japan', population: 126960000}
   ]

   console.log(mostPopulatedCountries(countries, 3))
   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000}
   ]
   ```
  function mostSpokenLanguages (countries,limit){
    const allLanguages = countries.flatMap(country => country.languages);

    const languageCount = allLanguages.reduce((acc,lang) =>{
      acc[lang] = (acc[lang] || 0) + 1;
      return acc;
    }, {});

    const sortedLanguages = Object.entries(languageCount)
    .map(([language, count]) => ({country: language, count}))
    .sort((a,b) => b.count - a.count);

    return sortedLanguages.slice(0,limit);
  }
  console.log(mostSpokenLanguages(countries, 10))
   ````

1. \*\*\* Intenta desarrollar un programa que calcule la medida de tendencia central de una muestra(mean, median, mode) y medida de la variabilidad(range, variance, standard deviation). Además de esas medidas, encuentre el mínimo, el máximo, el recuento, el porcentaje y la distribución de frecuencias de la muestra. Puede crear un objeto llamado estadísticas y crear todas las funciones que hacen cálculos estadísticos como método para el objeto estadísticas. Comprueba el resultado que aparece a continuación.

   ```js
   const ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

   console.log('Count:', statistics.count()) // 25
   console.log('Sum: ', statistics.sum()) // 744
   console.log('Min: ', statistics.min()) // 24
   console.log('Max: ', statistics.max()) // 38
   console.log('Range: ', statistics.range() // 14
   console.log('Mean: ', statistics.mean()) // 30
   console.log('Median: ',statistics.median()) // 29
   console.log('Mode: ', statistics.mode()) // {'mode': 26, 'count': 5}
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Standard Deviation: ', statistics.std()) // 4.2
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Frequency Distribution: ',statistics.freqDist()) # [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

   ```sh
   console.log(statistics.describe())
   Count: 25
   Sum:  744
   Min:  24
   Max:  38
   Range:  14
   Mean:  30
   Median:  29
   Mode:  (26, 5)
   Variance:  17.5
   Standard Deviation:  4.2
   Frequency Distribution: [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

   const statistics = {
  data: [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26],

  // 1️⃣ Contar cuántos elementos hay en la lista
  count() {
    return this.data.length;
  },

  // 2️⃣ Sumar todos los elementos de la lista
  sum() {
    return this.data.reduce((acc, num) => acc + num, 0);
  },

  // 3️⃣ Obtener el valor mínimo
  min() {
    return Math.min(...this.data);
  },

  // 4️⃣ Obtener el valor máximo
  max() {
    return Math.max(...this.data);
  },

  // 5️⃣ Calcular el rango (máximo - mínimo)
  range() {
    return this.max() - this.min();
  },

  // 6️⃣ Calcular la media (promedio)
  mean() {
    return Math.round(this.sum() / this.count());
  },

  // 7️⃣ Calcular la mediana
  median() {
    const sorted = [...this.data].sort((a, b) => a - b);
    const mid = Math.floor(sorted.length / 2);

    return sorted.length % 2 === 0
      ? (sorted[mid - 1] + sorted[mid]) / 2
      : sorted[mid];
  },

  // 8️⃣ Calcular la moda (número que más se repite)
  mode() {
    const freq = {};
    this.data.forEach(num => (freq[num] = (freq[num] || 0) + 1));

    let maxCount = 0;
    let modeValue = null;

    for (const num in freq) {
      if (freq[num] > maxCount) {
        maxCount = freq[num];
        modeValue = Number(num);
      }
    }

    return { mode: modeValue, count: maxCount };
  },

  // 9️⃣ Calcular la varianza
  var() {
    const mean = this.mean();
    const squaredDiffs = this.data.map(num => Math.pow(num - mean, 2));
    return parseFloat((squaredDiffs.reduce((acc, val) => acc + val, 0) / this.count()).toFixed(2));
  },

  // 🔟 Calcular la desviación estándar
  std() {
    return parseFloat(Math.sqrt(this.var()).toFixed(2));
  },

  // 1️⃣1️⃣ Calcular la distribución de frecuencias
  freqDist() {
    const freq = {};
    this.data.forEach(num => (freq[num] = (freq[num] || 0) + 1));

    const sortedFreq = Object.entries(freq)
      .map(([num, count]) => [(count / this.count()) * 100, Number(num)])
      .sort((a, b) => b[0] - a[0]);

    return sortedFreq;
  },

  // 1️⃣2️⃣ Describir todas las estadísticas
  describe() {
    console.log(`Count: ${this.count()}`);
    console.log(`Sum: ${this.sum()}`);
    console.log(`Min: ${this.min()}`);
    console.log(`Max: ${this.max()}`);
    console.log(`Range: ${this.range()}`);
    console.log(`Mean: ${this.mean()}`);
    console.log(`Median: ${this.median()}`);
    console.log(`Mode: (${this.mode().mode}, ${this.mode().count})`);
    console.log(`Variance: ${this.var()}`);
    console.log(`Standard Deviation: ${this.std()}`);
    console.log(`Frequency Distribution: ${JSON.stringify(this.freqDist())}`);
  }
};

// Ejecutar el método describe para mostrar las estadísticas
statistics.describe();


🎉 ¡FELICITACIONES! 🎉

[<< Día 8](../dia_08_Objetos/dia_08_objetos.md) | [Día 10 >>](../dia_10_Sets_y_Maps/dia_10_sets_y_maps.md)
