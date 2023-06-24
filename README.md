# Arrow-Functions

Las arrow functions, también conocidas como funciones flecha, son una forma más concisa de escribir funciones en JavaScript y TypeScript. Proporcionan una sintaxis más compacta y tienen un comportamiento especial en cuanto al valor de `this`.

Ejemplo básico de una arrow function en TypeScript:

```typescript
const sum = (a: number, b: number): number => {
  return a + b;
};
```

En este ejemplo, se declara una arrow function llamada `sum` que recibe dos parámetros `a` y `b` de tipo `number`. La función retorna la suma de los dos parámetros. La anotación de tipo `: number` al final de la función indica que la función retorna un valor de tipo `number`.

Uso de la arrow function:

```typescript
console.log(sum(2, 3));  // Output: 5
```

En este caso, se llama a la función `sum` con los argumentos `2` y `3`, y se muestra el resultado de la suma en la consola.

Características de las arrow functions:

1. Sintaxis concisa: Las arrow functions permiten reducir la sintaxis de una función. Si la función tiene una sola expresión, se puede omitir el bloque de llaves y la declaración de `return` se realiza implícitamente.

```typescript
const double = (num: number): number => num * 2;
```

2. `this` léxico: Una de las características más destacadas de las arrow functions es que no crean su propio contexto de `this`. En su lugar, utilizan el `this` del contexto que las rodea.

```typescript
const person = {
  name: "John",
  greet: function() {
    setTimeout(() => {
      console.log(`Hello, my name is ${this.name}`);
    }, 1000);
  }
};

person.greet();  // Output: Hello, my name is John
```

En este ejemplo, la arrow function en el `setTimeout` accede correctamente a la propiedad `name` del objeto `person`, ya que utiliza el `this` del contexto de `greet`.

Las arrow functions son muy útiles para escribir código más conciso y legible en TypeScript. Son especialmente útiles en situaciones donde se necesita preservar el contexto de `this` y evitar el uso de funciones anónimas.
