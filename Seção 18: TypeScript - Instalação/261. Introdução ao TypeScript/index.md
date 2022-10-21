# 261. Introdução ao TypeScript

## Definição

TypeScript é um superset do Javascript e compila para Javascript puro.

## Adiciona tipagem estática ao JavaScript

```js
// Javascript puro
function multiplyNumbers(x, y) {
  return x * y;
}

const result = multiplyNumbers(10, [1, 2]);
console.log(result); // NaN
```

```ts
// TypeScript
function multiplyNumbers(x: number, y: number) {
  return x * y;
}

// O editor de código vai alertar o vetor [1, 2]
const result = multiplyNumbers(10, [1, 2]);
console.log(result); // NaN
```

## Adiciona novos recursos ao JavaScript

```ts
interface TemNome {
  nome: string;
}

interface TemSobrenome {
  sobrenome: string;
}

class Aluno implements TemNome, TemSobrenome {
  constructor(
    public readonly nome: string,
    public readonly sobrenome: string,
    private readonly idade: number,
  ) {}
}

const aluno = new Aluno('Luiz', 'Otávio', 30);
console.log(aluno)
// Aluno { nome: 'Luiz', sobrenome: 'Otávio', idade: 30 }
```

```ts
abstract class Animal {
  abstract makeNoise(): void;
}

class Dog extends Animal {
  constructor(private readonly name: string) {
    super();
  }

  makeNoise(): void {
    console.log(`${this.name} is barking.`);
  }
}

const dog = new Dog('Tina');
dog.makeNoise(); // Tina is barking.
```

É multi-paradigma e faz tudo que o Javascript faz.

```ts
type CalculatorFn = (x: number, y: number) => number;

const add: CalculatorFn = (x, y) => x + y;
const sub: CalculatorFn = (x, y) => x - y;
const mul: CalculatorFn = (x, y) => x * y;
const div: CalculatorFn = (x, y) => x / y;

const twoPlusTwo = add(2, 2); // 4
const twoMinusTwo = sub(2, 2); // 0
const twoTimesTwo = mul(2, 2); // 4
const twoDividedByTwo = div(2, 2); // 1
```

```ts
// "enum"...
type ProgrammingLanguages = 'Python' | 'JavaScript' | 'TypeScript';

function sayFavoriteProgrammingLanguage(language: ProgrammingLanguages) {
  return `You like ${language}`;
}

const favoriteLanguage = sayFavoriteProgrammingLanguage('TypeScript');
console.log(favoriteLanguage);
```

## lib.es5.d.ts

Declaration file, ou biblioteca de métodos

## Modela os tipos com inferência de tipos

```ts
const pessoa {
  nome: 'Luiz',
  sobrenome: 'Otávio',
  idade: 30
}

const pessoa {
  nome: string,
  sobrenome: string,
  idade: number
}
```
