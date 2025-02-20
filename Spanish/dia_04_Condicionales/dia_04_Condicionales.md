<div align="center">
  <h1> 30 Días de JavaScript: Condicionales</h1>
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

[<< Día 3](../dia_03_Booleanos_Operadores_Date/dia_03_Boleanos_Operadores_Date.md) | [Día 5 >>](../dia_05_Arreglos/dia_05_arreglos.md)

![Thirty Days Of JavaScript](../images/banners/day_1_4.png)

- [📔 Día 4](#📔-día-4)
  - [Condicionales](#condicionales)
    - [If](#if)
    - [If Else](#if-else)
    - [If Else if Else](#if-else-if-else)
    - [Switch](#switch)
    - [Operadores Ternarios](#operadores-ternarios)
  - [💻 Ejercicios](#💻-ejercicios)
    - [Ejercicios: Nivel 1](#ejercicios-nivel-1)
    - [Ejercicios: Nivel 2](#ejercicios-nivel-2)
    - [Ejercicios: Nivel 3](#ejercicios-nivel-3)

# 📔 Día 4

## Condicionales

Las declaraciones condicionales se utilizan para tomar decisiones basadas en diferentes condiciones. De forma predeterminada, las declaraciones en el script de JavaScript se ejecutan secuencialmente de arriba a abajo. Si la lógica de procesamiento lo requiere, el flujo secuencial de ejecución se puede alterar de dos formas:

- Ejecución condicional: se ejecutará un bloque de una o más sentencias si cierta expresión es true
- Ejecución repetitiva: un bloque de una o más sentencias se ejecutará de forma repetitiva siempre que cierta expresión sea verdadera. En esta sección, cubriremos las declaraciones _if_, _else_ y _else if_. Los operadores lógicos y de comparación que aprendimos en las secciones anteriores serán útiles aquí.

Las condiciones se pueden implementar de las siguientes maneras:

- if
- if else
- if else if else
- switch
- operador ternario

### If

En JavaScript y otros lenguajes de programación, la palabra clave _if_ se usa para verificar si una condición es true y ejecutar el bloque de código. Para crear una condición if, necesitamos la palabra clave _if_, la condición va dentro de paréntesis y el bloque de código va dentro de llaves ({}).

```js
// sintaxis
if (condition) {
  //esta parte del código se ejecuta cuando es true
}
```

**Example:**

```js
let num = 3;
if (num > 0) {
  console.log(`${num} es un número positivo`);
}
//  3 es un número positivo
```

Como puede ver en el ejemplo de condición anterior, 3 es mayor que 0, por lo que es un número positivo. La condición era true y se ejecutó el bloque de código. Sin embargo, si la condición es falsa, no veremos ningún resultado.

```js
let isRaining = true;
if (isRaining) {
  console.log("Recuerda llevar tu impermeable.");
}
```

Lo mismo ocurre con la segunda condición, si isRaining es false, el bloque if no se ejecutará y no veremos ninguna respuesta. Para ver el resultado de una condición false, debemos tener otro bloque, que será _else_.

### If Else

Si la condición es true, se ejecutará el primer bloque, si no, se ejecutará la condición else.

```js
// sintaxis
if (condition) {
  // esta parte del código se ejecuta para la condición de verdad
} else {
  // esta parte del código se ejecuta para una condición falsa
}
```

```js
let num = 3;
if (num > 0) {
  console.log(`${num} es un número positivo`);
} else {
  console.log(`${num} es un número negativo`);
}
//  3 es un número positivo

num = -3;
if (num > 0) {
  console.log(`${num} es un número positivo`);
} else {
  console.log(`${num} es un número negativo`);
}
//  -3 es un número negativo
```

```js
let isRaining = true;
if (isRaining) {
  console.log("Necesitas un impermeable.");
} else {
  console.log("No hay necesidad de un impermeable.");
}
// Necesitas un impermeable.

isRaining = false;
if (isRaining) {
  console.log("Necesitas un impermeable.");
} else {
  console.log("No hay necesidad de un impermeable.");
}
// No hay necesidad de un impermeable.
```

La última condición es falsa, por lo que se ejecutó el bloque else. ¿Qué pasa si tenemos más de dos condiciones? En ese caso, usaremos las condiciones _else if_.

### If Else if Else

En nuestra vida, tomamos decisiones diariamente. Tomamos decisiones no comprobando una o dos condiciones, sino que tomamos decisiones basadas en múltiples condiciones. Al igual que nuestra vida diaria, la programación también está llena de condiciones. Usamos _else if_ cuando tenemos múltiples condiciones.

```js
// sintaxis
if (condition) {
  // código
} else if (condition) {
  // código
} else {
  //  código
}
```

**Ejemplo:**

```js
let a = 0;
if (a > 0) {
  console.log(`${a} es un número positivo`);
} else if (a < 0) {
  console.log(`${a} es un número negativo`);
} else if (a == 0) {
  console.log(`${a} es cero`);
} else {
  console.log(`${a} no es un número`);
}
```

```js
// if else if else
let weather = "sunny";
if (weather === "rainy") {
  console.log("Necesitas un impermeable.");
} else if (weather === "cloudy") {
  console.log("Puede que haga frío, necesitas una chaqueta.");
} else if (weather === "sunny") {
  console.log("Sal tranquilo.");
} else {
  console.log("No hay necesidad de un impermeable.");
}
```

### Switch

Switch es una alternativa para **if else if else else**.
La instrucción switch comienza con una palabra clave _switch_ seguida de un paréntesis y un bloque de código. Dentro del bloque de código tendremos diferentes casos. El bloque de casos se ejecuta si el valor en el paréntesis de la declaración de cambio coincide con el valor del caso. La declaración de break es para terminar la ejecución. Esto para que la ejecución del código se detenga después de que se cumpla la condición. El bloque default se ejecuta si todos los casos no cumplen la condición.

```js
switch (caseValue) {
  case 1:
    // código
    break;
  case 2:
    // código
    break;
  case 3:
    // código
    break;
  default:
  // código
}
```

```js
let weather = "cloudy";
switch (weather) {
  case "rainy":
    console.log("Necesitas un impermeable.");
    break;
  case "cloudy":
    console.log("Puede que haga frío, necesitas una chaqueta.");
    break;
  case "sunny":
    console.log("Sal tranquilo.");
    break;
  default:
    console.log("No hay necesidad de un impermeable.");
}

// Más Ejemplos switch
let dayUserInput = prompt("¿Qué día es hoy?");
let day = dayUserInput.toLowerCase();

switch (day) {
  case "lunes":
    console.log("Hoy es Lunes");
    break;
  case "martes":
    console.log("Hoy es Martes");
    break;
  case "miércoles":
    console.log("Hoy es Miércoles");
    break;
  case "jueves":
    console.log("Hoy es Jueves");
    break;
  case "viernes":
    console.log("Hoy es Viernes");
    break;
  case "sábado":
    console.log("Hoy es Sábado");
    break;
  case "domingo":
    console.log("Hoy es Domingo");
    break;
  default:
    console.log("No es un día de semana.");
}
```

// Ejemplos de condiciones en los casos

```js
let num = prompt("Ingrese un número");
switch (true) {
  case num > 0:
    console.log("El número es positivo");
    break;
  case num == 0:
    console.log("El número es cero");
    break;
  case num < 0:
    console.log("El número es negativo");
    break;
  default:
    console.log("El valor ingresado no era un número");
}
```

### Operadores Ternarios

Otra forma de escribir condicionales es usando operadores ternarios. Hemos cubierto esto en otras secciones, pero también deberíamos mencionarlo aquí.

```js
let isRaining = true;
isRaining
  ? console.log("Necesitas un impermeable.")
  : console.log("No hay necesidad de un impermeable.");
```

🌕 Tienes una energía ilimitada. Acabas de completar los desafíos del día 4 y llevas cuatro pasos de tu camino hacia la grandeza. Ahora haz algunos ejercicios para tu cerebro y tus músculos.

## 💻 Ejercicios

### Ejercicios: Nivel 1

1. Obtenga la entrada del usuario usando el aviso ("Ingrese su edad:"). Si el usuario tiene 18 años o más, muestre el mensaje: 'Tiene la edad suficiente para conducir', pero si no tiene 18 años, brinde otro mensaje que indique que debe esperar la cantidad de años que necesita para cumplir 18.

   ```sh
   Ingrese su edad: 30
   Tiene la edad suficiente para conducir.

   Ingrese su edad:15
   Te faltan 3 años para conducir.

  let edad = prompt ('Ingrese su edad')
   edad = parseFloat (edad)

  if (isNaN(edad)) {
    alert('Inserta caracateres tipo numero')
  }else if (edad >= 18){
    alert('Tienes la edad suficiente para conducir')
  }else{
       let operacion = 18 - edad
    alert(`te faltan ${operacion} años para conducir`)
  }
   ```

1. Compara los valores de myAge y yourAge usando if... else. Según la comparación, registre el resultado en la consola indicando quién es mayor (tú o yo). Utilice prompt(“Ingrese su edad:”) para obtener la edad como entrada.

   ```sh
   Ingrese su edad: 30
   Eres 5 años mayor que yo.

  let myAge = prompt('Ingresa tu edad')
   let yourAge = 22

   if (isNaN(myAge)){
    alert('Valores incorrectos')
   }else if (myAge > yourAge){
    let opera = Math.abs(myAge - yourAge)
    console.log(`Eres ${opera} mayor que yo`)
   }else{
         let opera = Math.abs(myAge - yourAge)
  console.log(`Yo soy mayor por ${opera} años`)
   }
   ```

1. Si a es mayor que b, devuelve 'a es mayor que b'; de lo contrario, 'a es menor que b'. Trate de implementarlo de maneras diferentes

   - Usando if else
   - operador ternario.

   ```js
   let a = 4;
   let b = 3;

   if (a>b){
    console.log(`${a} es mayor que ${b}`)
   }else{
    console.log(`${b} es mayor que ${a}`)
   }

    a > b ?console.log(`${a} es mayor que ${b}`) : console.log(`${b} es mayor que ${a}`)

   ```

   ```sh
     4 es mayor que 3
   ```

1. Los números pares son divisibles por 2 y el resto es cero. ¿Cómo verificar si un número es par o no usando JavaScript?

   ```sh
   Ingrese un número: 2
   2 es un número par

   Ingrese un número: 9
   9 es un número impar


   let numero = prompt ('Ingres un numero')
   numero = parseFloat (numero)

   if (isNaN (numero)){
    alert('ingrese valores numericos')
   } else if (numero % 2 === 0 ){
    alert (`Felicidades ${numero} es par`)
   }else{
    alert(`Lo siento ${numero} no es par`)
   }
   ```

### Ejercicios: Nivel 2

1. Escriba un código que pueda calificar a los estudiantes de acuerdo con sus puntajes:
   - 80-100, A
   - 70-89, B
   - 60-69, C
   - 50-59, D
   - 0-49, F

  let calificacion = prompt('Ingresa su calificacion')
   calificacion = parseFloat(calificacion)
  
  if (isNaN(calificacion) ){
    alert('Añade valores numericos')
 }else if (calificacion >=0){
      alert(`Tu calificacion fue ${calificacion} tienes una F`)
  }else if(calificacion >=49){
    alert(`Tu calificacion fue ${calificacion} tienes una F`)
  }else if (calificacion >=59){
        alert(`Tu calificacion fue ${calificacion} tienes una D`)
  }else if (calificacion >=69){
        alert(`Tu calificacion fue ${calificacion} tienes una C`)
  }else if(calificacion>=89){
        alert(`Tu calificacion fue ${calificacion} tienes una B`)
  }else if (calificacion>=100){
        alert(`Tu calificacion fue ${calificacion} tienes una A`)
  }else{
    alert('agregea un valor')
  }
  /*CODIGO MEJORADO /*
  let calificacion = prompt('Ingresa tu calificación');
calificacion = parseFloat(calificacion);

if (isNaN(calificacion)) {
    alert('Por favor, ingresa un valor numérico válido');
} else if (calificacion >= 80 && calificacion <= 100) {
    alert(`Tu calificación fue ${calificacion}. Tienes una A.`);
} else if (calificacion >= 70 && calificacion <= 79) {
    alert(`Tu calificación fue ${calificacion}. Tienes una B.`);
} else if (calificacion >= 60 && calificacion <= 69) {
    alert(`Tu calificación fue ${calificacion}. Tienes una C.`);
} else if (calificacion >= 50 && calificacion <= 59) {
    alert(`Tu calificación fue ${calificacion}. Tienes una D.`);
} else if (calificacion >= 0 && calificacion <= 49) {
    alert(`Tu calificación fue ${calificacion}. Tienes una F.`);
} else {
    alert('Por favor, ingresa una calificación válida entre 0 y 100.');
}

  
   
1. Consulta si la temporada es Otoño, Invierno, Primavera o Verano.
   Si la entrada del usuario es :

   - Septiembre, Octubre o Noviembre, la temporada es Otoño.
   - Diciembre, Enero o Febrero, la temporada es Invierno.
   - Marzo, Abril o Mayo, la temporada es Primavera
   - Junio, Julio o Agosto, la temporada es Verano

let Month = prompt('Ingresa tu Mes')
  let clima = Month.toLowerCase();

  switch(clima){
    case "septiembre":
    case "octubre":
    case "noviembre":
    alert('Estamos en temporada de Otoño!')
    break;

    case "diciembre":
    case  "enero":
    case  "febrero":
    alert('Estamos en temporada de invierno!')
    break;

    case "marzo":
    case "abril":
    case "mayo":
    alert('Estamos en temporada de Primavera!')
    break;

    case "junio":
    case "julio":
    case "agosto":
    alert('Estamos en Verano!') 
    break;
      default:
    alert('Eso no es es un mes')
  }

1. Compruebe si un día es un día de fin de semana o un día laborable. Su script tomará el día como entrada.

```sh
    ¿Qué día es hoy? Sábado
    El sábado es fin de semana.

    ¿Qué día es hoy? sábAdo
    El sábado es fin de semana.

    ¿Qué día es hoy? Viernes
    El viernes es un día laborable.

    ¿Qué día es hoy? ViErNes
    El viernes es un día laborable.

    let dia = prompt('Ingresa tu dia')
    let day = dia.toLowerCase();

    switch(day){

      case "lunes":
      case "martes":
      case "miercoles":
      case "jueves":
      case "viernes":
      alert(`${day} un dia laborable`)
      break;
      case "sabado":
      case "domingo":
      alert(`${day} es un fin de semana`)
      break;
      default:
      alert('Ese no es un dia')
    }
```

### Ejercicios: Nivel 3

1. Escribe un programa que diga el número de días en un mes.

```sh
  Introduce un mes: Enero
  Enero tiene 31 días.

  Introduce un mes: ENERO
  enero tiene 31 dias

  Introduce un mes: Febrero
  Febrero tiene 28 días.

  Introduce un mes: FEbrero
  Febrero tiene 28 días.

  let month = prompt('Ingresa tu mes');
  let diaMes = month.toLowerCase();
  let primeraMes  = diaMes.charAt(0).toUpperCase() + diaMes.slice(1);

  switch (diaMes){
    case "enero":
    case "marzo":
    case "mayo":
    case "julio":
    case "agosto":
    case "octubre":
    case "diciembre":
    alert(`${primeraMes} tiene 31 dias`)
    break;
    case "febrero":
    alert(`${primeraMes} tiene 28 dias`)
    break;
    case "abril":
    case "junio":
    case "septiembre":
    case "noviembre":
    alert(`${primeraMes} tiene 30 dias`)
    break;
    default :
    alert('Ese no es un mes') 

  }

  
  */ IMPLEMENTADO EN IF /*
  let month = prompt('Ingresa tu mes');
  let diaMes = month.toLowerCase(); // Convertimos el texto a minúsculas
  let primeraMes = diaMes.charAt(0).toUpperCase() + diaMes.slice(1); // Para mostrar la primera letra en mayúscula

  if (diaMes === "enero" || diaMes === "marzo" || diaMes === "mayo" || diaMes === "julio" ||
    diaMes === "agosto" || diaMes === "octubre" || diaMes === "diciembre") {
  alert(`${primeraMes} tiene 31 días`);
  } else if (diaMes === "febrero") {
  alert(`${primeraMes} tiene 28 días`);
  } else if (diaMes === "abril" || diaMes === "junio" || diaMes === "septiembre" || diaMes === "noviembre") {
  alert(`${primeraMes} tiene 30 días`);
  } else {
  alert('Ese no es un mes');
  }
```

1. Escribe un programa que diga el número de días en un mes, ahora considera un año bisiesto.
let mes = prompt ('ingresa tu mes')
let ano = prompt ('ingresa tu año')
ano = parseInt (ano)
let chicaFrase = mes.toLowerCase();
let primeraFrase = mes.charAt(0).toUpperCase() + mes.slice(1);

function bisiesto (ano){
return (ano % 4 === 0 &&  ano % 100 !== 0 || ano % 400 === 0)
}

if (chicaFrase === "enero" || chicaFrase === "marzo" || chicaFrase === "mayo" || chicaFrase === "julio" || chicaFrase === "agosto" || chicaFrase === "octubre" || chicaFrase === "diciembre"){
  alert (`${primeraFrase} tiene 31 dias`)
}else if (chicaFrase === "febrero"){
  if (bisiesto (ano)){
    alert(`${primeraFrase} tiene 29 dias porque ${ano} es bisiesto`)
  } else{
    alert(`${primeraFrase} tiene 28 dias porque ${ano} no es bisiesto`)
  }
}else if (chicaFrase === "abril" || chicaFrase === "junio" || chicaFrase === "septiembre" || chicaFrase === "noviembre"){
alert(`${primeraFrase} tiene 30 dias`)
}else{
  alert('ese no es un mes ni  un año existente')
}


🎉 FELICITACIONES ! 🎉

[<< Día 3](../dia_03_Booleanos_Operadores_Date/dia_03_Boleanos_Operadores_Date.md) | [Día 5 >>](../dia_05_Arreglos/dia_05_arreglos.md)
