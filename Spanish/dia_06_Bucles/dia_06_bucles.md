<div align="center">
  <h1> 30 Días de JavaScript: Bucles</h1>
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

[<< Día 5](../dia_05_Arreglos/dia_05_arreglos.md) | [ Día 7 >>](../dia_07_Funciones/dia_07_funciones.md)

![Day 6](../images/banners/day_1_6.png)

- [📔 Día 6](#📔-día-6)
  - [Bucles](#bucles)
    - [Bucle for](#bucle-for)
    - [Bucle while](#bucle-while)
    - [Bucle do while](#bucle-do-while)
    - [Bucle for of](#bucle-for-of)
    - [break](#break)
    - [continue](#continue)
  - [💻 Ejercicios: Día 6](#💻-ejerciciosdía-6)
    - [Ejercicios: Nivel 1](#ejercicios-nivel-1)
    - [Ejercicios: Nivel 2](#ejercicios-nivel-2)
    - [Ejercicios: Nivel 3](#ejercicios-nivel-3)

# 📔 Día 6

## Bucles

La mayoría de las actividades que hacemos en la vida están llenas de repeticiones. Imagina que tienes que imprimir de 0 a 100 usando console.log(). Para implementar esta simple tarea, puede tomar de 2 a 5 minutos, este tipo de tarea tediosa y repetitiva se puede llevar a cabo usando un bucle. Si prefieres ver los videos, puedes revisar el [video tutorials](https://www.youtube.com/channel/UCM4xOopkYiPwJqyKsSqL9mw)

En los lenguajes de programación para realizar tareas repetitivas utilizamos diferentes tipos de bucles. Los siguientes ejemplos son los bucles de uso común en JavaScript y otros lenguajes de programación.

### Bucle for

```js
// Estructura del bucle for
for(inicialización, condición, incremento/decremento){
  // el código va aquí
}
```

```js
for (let i = 0; i <= 5; i++) {
  console.log(i);
}

// 0 1 2 3 4 5
```

```js
for (let i = 5; i >= 0; i--) {
  console.log(i);
}

// 5 4 3 2 1 0
```

```js
for (let i = 0; i <= 5; i++) {
  console.log(`${i} * ${i} = ${i * i}`);
}
```

```sh
0 * 0 = 0
1 * 1 = 1
2 * 2 = 4
3 * 3 = 9
4 * 4 = 16
5 * 5 = 25
```

```js
const countries = ["Finland", "Sweden", "Denmark", "Norway", "Iceland"];
const newArr = [];
for (let i = 0; i < countries.length; i++) {
  newArr.push(countries[i].toUpperCase());
}

// ["FINLAND", "SWEDEN", "DENMARK", "NORWAY", "ICELAND"]
```

Agregar todos los elementos en un array

```js
const numbers = [1, 2, 3, 4, 5];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  sum = sum + numbers[i]; // can be shorten, sum += numbers[i]
}

console.log(sum); // 15
```

Crea un nuevo array basado en el array existente

```js
const numbers = [1, 2, 3, 4, 5];
const newArr = [];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  newArr.push(numbers[i] ** 2);
}

console.log(newArr); // [1, 4, 9, 16, 25]
```

```js
const countries = ["Finland", "Sweden", "Norway", "Denmark", "Iceland"];
const newArr = [];
for (let i = 0; i < countries.length; i++) {
  newArr.push(countries[i].toUpperCase());
}

console.log(newArr); // ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

### Bucle while

```js
let i = 0;
while (i <= 5) {
  console.log(i);
  i++;
}

// 0 1 2 3 4 5
```

### Bucle do while

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i <= 5);

// 0 1 2 3 4 5
```

### Bucle for of

Usamos el bucle for of para arrays. Es una forma muy práctica de iterar a través de un array, si no estamos interesados en el index de cada elemento del array.

```js
for (const element of arr) {
  // el código va aquí
}
```

```js
const numbers = [1, 2, 3, 4, 5];

for (const num of numbers) {
  console.log(num);
}

// 1 2 3 4 5

for (const num of numbers) {
  console.log(num * num);
}

// 1 4 9 16 25

// sumando todos los números del array
let sum = 0;
for (const num of numbers) {
  sum = sum + num;
  // también se puede acortar así, sum += num
  // después de esto usaremos la sintaxis más corta (+=, -=, *=, /= etc)
}
console.log(sum); // 15

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

for (const tech of webTechs) {
  console.log(tech.toUpperCase());
}

// HTML CSS JAVASCRIPT REACT NODE MONGODB

for (const tech of webTechs) {
  console.log(tech[0]); // obtiene solo la primera letra de cada elemento,  H C J R N M
}
```

```js
const countries = ["Finland", "Sweden", "Norway", "Denmark", "Iceland"];
const newArr = [];
for (const country of countries) {
  newArr.push(country.toUpperCase());
}

console.log(newArr); // ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

### break

Break se utiliza para interrumpir un bucle.

```js
for (let i = 0; i <= 5; i++) {
  if (i == 3) {
    break;
  }
  console.log(i);
}

// 0 1 2
```

El código anterior se detiene si se encuentran 3 en el proceso de iteración.

### continue

Usamos la palabra clave _continue_ para omitir ciertas iteraciones.

```js
for (let i = 0; i <= 5; i++) {
  if (i == 3) {
    continue;
  }
  console.log(i);
}

// 0 1 2 4 5
```

🌕 Tienes una energía ilimitada. Acabas de completar los desafíos del día 6 y llevas seis pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Ejercicios:Día 6

### Ejercicios: Nivel 1

```js
const countriess = [
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

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

const mernStack = ["MongoDB", "Express", "React", "Node"];
```

1. Itera de 0 a 10 usando el bucle for, haga lo mismo usando los bucles while y do while
    //FOR
    for (let i = 0; i <= countriess.length; i ++){
      console.log(countriess[i])
    }
    //WHILE

    let i =0;
    while(i<=webTechs.length){
      console.log(webTeach[i])
      i++
    }

  //DO WHILE
      let i =0;
do{
        console.log(mernStack[i])
      i++
}while(i<=mernStack.length)

2. Itera 10 to 0 usando el bucle for, haga lo mismo usando los bucles while y do while
    for (let i = 10; i >= 10; i--){
      console.log(i)
    }

      //WHILE
      let i = 10;
      while(i>=0){
        console.log(i);
        i--
      }

      //DO WHILE 
       
       let i = 10;
       do{
        console.log(i)
        i --
       }while(i>=0)

3. Itera de 0 a n usando el bucle for
  let n = 20;
  for (let i = n; i >= 0; i-- ){
    console.log(i)
  }
4. Escribe un bucle que haga el siguiente patrón usando console.log():

   ```js
       #
       ##
       ###
       ####
       #####
       ######
       #######
   ```
   for (let i = 1; i<=gato; i++){
  console.log("#".repeat(i));
   }

5. Usa un bucle para imprimir el siguiente patrón:

   ```sh
   0 x 0 = 0
   1 x 1 = 1
   2 x 2 = 4
   3 x 3 = 9
   4 x 4 = 16
   5 x 5 = 25
   6 x 6 = 36
   7 x 7 = 49
   8 x 8 = 64
   9 x 9 = 81
   10 x 10 = 100

   for(let i=0; i<=10; i++){
    console.log(`${i} * ${i} = ${i * i}`)
   }
   ```

6. Usando un bucle imprime el siguiente patrón:

   ```sh
    i    i^2   i^3
    0    0     0
    1    1     1
    2    4     8
    3    9     27
    4    16    64
    5    25    125
    6    36    216
    7    49    343
    8    64    512
    9    81    729
    10   100   1000

  console.log('i    i^2    i^3');
  for (let i = 0; i <= 10; i++) {
  console.log(`${i}    ${i * i}    ${i * i * i}`);
  }
   ```

7. Usa el bucle for para iterar de 0 a 100 e imprima solo números pares
    arrayPar = [];
    arrayImpar = [];

    for (let i = 0; i<=100; i++ ){
    if (i % 2 === 0 ){
      arrayPar.push(i);
    }else{
      arrayImpar.push(i);
    }
    }
  console.log('Pares:', arrayPar)
  console.log('Impares:', arrayImpar)

8. Usa el bucle for para iterar de 0 a 100 e imprima solo números impares
  arrayImpar = [];

  for (let i = 0; i <= 100; i++) {
  if (i % 2 !== 0) {
    arrayImpar.push(i);
  }
  }

console.log('Impares:', arrayImpar);

9. Usa el bucle for para iterar de 0 a 100 e imprima los solo números primos
  function esPrimo(n) {
  if (n <= 1) return false; // Los números menores o iguales a 1 no son primos.
  for (let i = 2; i <= Math.sqrt(n); i++) {
    if (n % i === 0) {
      return false; // Encontramos un divisor, no es primo.
    }
  }
  return true; // Si no encontramos divisores, es primo.
}


10. Usa el bucle for para iterar de 0 a 100 e imprima la suma de todos los números.
  
    ```sh
    La suma de todos los números de 0 a 100 es 5050.
      let sum = 0;
  for(let i = 0; i<=100; i++){
  sum = sum  + i;
  console.log(`el resultado es ${sum}`);
  }
    ```

11. Usa el bucle para iterar de 0 a 100 e imprimir la suma de todos los pares y la suma de todos los impares.

    ```sh
    La suma de todos los pares de 0 a 100 es 2550. Y la suma de todos los impares de 0 a 100 es 2500.
    let sumPar = 0;
    let sumImpar = 0;
    for(let i = 0; i<=100; i++){
      if(i % 2  === 0){
        sumPar = sumPar + i;
      }else{
        sumImpar= sumImpar + i;
      }
    }
    console.log(`la suma de los pares es ${sumPar}`)
    console.log(`la suma de los impares es ${sumImpar}`)
    ```

12. Usa el bucle para iterar de 0 a 100 e imprimir la suma de todos los pares y la suma de todos los impares. Imprimir suma de pares y suma de impares como un array

    ```sh
      [2550, 2500]
      sumPar= 0;
      sumImpar =0;
      let arrayMixed = [];

      for(let i = 0; i<=100; i++){
        if(i % 2 === 0){
          sumPar = sumPar +i;
        }else {
          sumImpar = sumImpar + i ; 
        }
      }
    arrayMixed.push(sumPar,sumImpar)
      console.log(arrayMixed)
    ```

13. Desarrolla un pequeño script que genera una matriz de 5 números aleatorios
      const matriz = [];
       min = 1;
        max = 5;

      for(let i = 0; i < 5; i++){
      const randomNumber = Math.floor(Math.random() * (max - min + 1) + min); //Si no incluyeras el + 1, nunca se alcanzaría el valor max.

    matriz.push(randomNumber);
      }
      console.log(matriz)

14. Desarrolla un pequeño script que genera una matriz de 5 números aleatorios. Los números debe ser únicos
      const matriz = [];
      min = 1;
      max =10;

      while (matriz.length < 5  ){
        const randomNumber = Math.floor(Math.random() * (max - min +1) + min)
        let existe = false;

      for (let i =0; i < matriz.length; i++){
        if(matriz[i] === randomNumber){
          existe = true;
        }
      }     
      
      if(!existe){
  matriz.push(randomNumber)
      }
  }     console.log(matriz)

15. Desarrolla un pequeño script que genera un id aleatorio de seis caracteres:

    ```sh
    5j2khz

      const caracteres = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
      id = "";
      for (let i = 0; i< 6; i++){
        const valoresRandom = Math.floor(Math.random() * caracteres.length)
        id = id + caracteres[valoresRandom];
      }
              console.log(id)

    ```

### Ejercicios: Nivel 2

1. Desarrolla un pequeño script que genera un id con cualquier número de caracteres aleatorios:

   ```sh
     fe3jo1gl124g

      const caracteres = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
      id = "";

      const longitud = Math.floor(Math.random() * (15 - 5 + 1)) + 5;

      for (let i = 0; i < longitud; i++){
        const valoresRandom = Math.floor(Math.random() * caracteres.length)
        id = id + caracteres[valoresRandom];
      }
              console.log(id)
   ```

   ```sh
     xkqci4utda1lmbelpkm03rba
   ```

1. Escribe un script que genere un número hexadecimal aleatorio.

   ```sh
   '#ee33df'

    const caracteresHex = "0123456789ABCDEF";
  let hexColor = "#";
    for ( let i = 0; i < 6; i++){
      const indexCaracter = Math.floor(Math.random() * caracteresHex.length)
      hexColor += caracteresHex[indexCaracter]
    }
    console.log(hexColor)
   ```

1. Escribe un script que genere un número de color rgb aleatorio.

   ```sh
   rgb(240,180,80)

  let colores = [];
  for (let i = 0; i < 3; i++) {
  // Generamos un número aleatorio para cada color
  colores.push(Math.floor(Math.random() * 256));
  }

 // Imprimir el valor RGB
 console.log(`rgb(${colores[0]}, ${colores[1]}, ${colores[2]})`);

    

1. Usando el array countries anterior, crea un array como el siguiente.
    const countriess = [
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
      let arrayMayus = [];

      for (let i = 0; i < countriess.length ; i++){
         let  mayus = countriess[i].toUpperCase();
          arrayMayus.push(mayus)
      }
            console.log(arrayMayus)


    ["ALBANIA", "BOLIVIA", "CANADA", "DENMARK", "ETHIOPIA", "FINLAND", "GERMANY", "HUNGARY", "IRELAND", "JAPAN", "KENYA"]
   ```

1. Usando el array countries anterior, crea un array para saber la longitud de cada país.

   ```sh


   let arrayMayus =  ["ALBANIA", "BOLIVIA", "CANADA", "DENMARK", "ETHIOPIA", "FINLAND", "GERMANY", "HUNGARY", "IRELAND", "JAPAN", "KENYA"]
        [7, 7, 6, 7, 8, 7, 7, 7, 7, 5, 5]

        let arrayNum =[];

        for (let i = 0; i < arrayMayus.length; i++){
          let pais = arrayMayus[i];
          let long = pais.length;
          arrayNum.push(recorr)
        } 
        console.log(arrayNum)
 
   ```

1. Utiliza el array countries para crear la siguiente array de arrays

   ```sh
   const countriies = ["Albania","Bolivia","Canada","Denmark","Ethiopia","Finland", "Germany","Hungary","Ireland", "Japan","Kenya",  ];

     [
     ['Albania', 'ALB', 7],
     ['Bolivia', 'BOL', 7],
     ['Canada', 'CAN', 6],
     ['Denmark', 'DEN', 7],
     ['Ethiopia', 'ETH', 8],
     ['Finland', 'FIN', 7],
     ['Germany', 'GER', 7],
     ['Hungary', 'HUN', 7],
     ['Ireland', 'IRE', 7],
     ['Iceland', 'ICE', 7],
     ['Japan', 'JAP', 5],
     ['Kenya', 'KEN', 5]
   ]
  const arrayPadre = [];

    for(let i = 0; i < countriies.length; i++ ){
        const arrayHijo=[];
        
        let pais = countriies[i];
        let tres = pais.slice(0, 3).toUpperCase();
        let long = pais.length;
        arrayHijo.push(pais, tres, long);
          arrayPadre.push(arrayHijo);

         }
         console.log(arrayPadre);
    
    

   ```

1. En el array countries anterior, verifica si hay un país que contenga la palabra 'land'. Si hay países que contienen 'land', imprimelo cono array. Si no hay ningún país que contenga la palabra'land', imprima 'Todos estos países no tienen la palabra land'.

   ```sh
   ['Finland','Ireland', 'Iceland']

    const countriies = ["Albania","Bolivia","Canada","Denmark","Ethiopia","Finland", "Germany","Hungary","Ireland", "Japan","Kenya",  ];
    const arrayNew =[];

      for (let i = 0; i < countriies.length; i++){
        let elemento = countriies[i];

        if(elemento.includes('land')){
          arrayNew.push(elemento)
        }else{
          console.log('Todos estos paises no tiene la palabra land')
        }
      }
      console.log(arrayNew)
   ```

1. En el array countries anterior, verifica si hay un país que termina con una subcadena (substring) 'ia'. Si hay países que terminan con 'ia', imprimelo como un array. Si no hay ningún país que contenga la palabra 'ia', imprime 'Estos países no terminan con ia'.

   ```sh
   ['Albania', 'Bolivia','Ethiopia']

    const countriies = ["Albania","Bolivia","Canada","Denmark","Ethiopia","Finland", "Germany","Hungary","Ireland", "Japan","Kenya",  ];
              const newPais =  [];

    for(let i = 0; i < countriies.length ; i++){
          let cadaUno = countriies[i];
          
          if(cadaUno.endsWith('ia')){
            newPais.push(cadaUno);
          }
    }
        if(newPais.length > 0 ){
              console.log(newPais)
          }else{
            console.log('estos paises no terminan con ia')
          }
    
   ```

1. Usando el array countries anterior, encuentre el país que contiene la mayor cantidad de caracteres.

   ```sh
   Ethiopia
    const countriies = ["Albania","Bolivia","Canada","Denmark","Ethiopia","Finland", "Germany","Hungary","Ireland", "Japan","Kenya",  ];
    let cadena = "";
    for(let i=0; i < countriies.length; i++){
      let tamano = countriies[i];
      if(tamano.length > cadena.length){
        cadena = tamano;
      }
    }
            console.log(`este es el pais mas largo ${cadena}`)

   ```

1. Usando el array countries anterior, encuentre el país que contiene sólo 5 caracteres.

   ```sh
   ['Japan', 'Kenya']
     const countriies = ["Albania","Bolivia","Canada","Denmark","Ethiopia","Finland", "Germany","Hungary","Ireland", "Japan","Kenya",  ];

     let paisActual = [];

     for (let i = 0; i < countriies.length; i++){
      let cadaUno = countriies[i];

      if(cadaUno.length === 5 ){
        paisActual.push(cadaUno);
      }
   }
    console.log(paisActual)

   ```

1. Encuentra la palabra más larga en el array webTechs
 const webTechs = ["HTML","CSS","JavaScript","React","Redux","Node","MongoDB",];

  let cadena = "";
  for(let i=0; i< webTechs.length; i++){
    let cadaUno = webTechs[i];
    if(cadaUno.length > cadena.length){
      cadena = cadaUno;
    }
  }
        console.log(`${cadena} es la palabra mas larga `)


1. Utiliza el array de webTechs para crear la el siguiente array de arrays:

   ```sh
   [["HTML", 4], ["CSS", 3],["JavaScript", 10],["React", 5],["Redux", 5],["Node", 4],["MongoDB", 7]]

 
   arrayPadre = [];
   for(let i= 0; i < webTechs.length; i++){
    arrayHijo = [];
    let cadaString = webTechs[i];
    let longitud = cadaString.length;
    arrayHijo.push(cadaString, longitud);
    arrayPadre.push(arrayHijo)
   }
   console.log(arrayPadre)
   ```

1. Una aplicación creada con MongoDB, Express, React y Node se denomina MERN stack app. Crea el acrónimo MERN usando el array mernStack
  const mernStack = ["MongoDB","Express","React","Node"]
            const AcroNimo = [];
    for(let i = 0; i < mernStack.length; i++){
      let primerLetra = mernStack[i][0];
      AcroNimo.push(primerLetra)
    }
          AcroNimo.join("")
    console.log(AcroNimo);
1. Iterar a través del array, ["HTML", "CSS", "JS", "React", "Redux", "Node", "Express", "MongoDB"] usando el bucle for o el bucle for of e imprime los elementos.
    const tecFront = ["HTML", "CSS", "JS", "React", "Redux", "Node", "Express", "MongoDB"];

    for(const tecn of tecFront){
      console.log(tecn);
    }


1. Este es un array de frutas, ['banana', 'orange', 'mango', 'lemon'] invierte el orden usando un bucle sin usar el método reverse().
      const fruts = ['banana', 'orange', 'mango', 'lemon'];
      for(let i = 0; i < fruts.length/2; i++) {
          let j = fruts.length-i-1;
          let a = fruts[i];
          fruts[i] = fruts[j];
          fruts[j]=a

      }
          console.log(fruts)
          

1. Imprime todos los elementos del array como se muestra a continuación:

   ```js
   const fullStack = [
     ["HTML", "CSS", "JS", "React"],
     ["Node", "Express", "MongoDB"],
   ];
   ```

   ```sh
     HTML
     CSS
     JS
     REACT
     NODE
     EXPRESS
     MONGODB

     for(const todo of fullStack){
        for(const var of todo){
          console.log(todo.toUpperCase())
        }
     }
   ```

### Ejercicios: Nivel 3

1. Copia el array countries (Evita mutaciones)
1. Los arrays son mutables. Crea una copia del array que no modifique el original. Ordena la copia del array y guárdala en una variable sortedCountries
1. Ordena el array webTechs y el array mernStack
1. Extrae todos los países que contengan la palabra 'land' del [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) e imprimela como un array
1. Encuentra el país que contiene la mayor cantidad de caracteres en el [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js)
1. Extrae todos los países que contienen la palabra 'land' del [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) e imprimela como un array
1. Extrae todos los países que contengan solo cuatro caracters del [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) e impremela como un array
1. Extrae todos los paíse que contengan dos o más palabras del [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) e imprimela como un array
1. Invertir el [array countries](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) y poner en mayúscula cada país y almacenalo en un array

🎉 ¡FELICITACIONES! 🎉

[<< Día 5](../dia_05_Arreglos/dia_05_arreglos.md) | [Día 7 >>](../dia_07_Funciones/dia_07_funciones.md)
