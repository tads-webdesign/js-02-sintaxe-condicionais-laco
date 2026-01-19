# js-02-sintaxe-condicionais-laco
Tutorial para Iniciantes: Controle do Fluxo de Execução em JavaScript

## Índice
1. [Estruturas Condicionais](#estruturas-condicionais)
2. [Operador Ternário](#operador-ternário)
3. [Switch Case](#switch-case)
4. [Loops (Laços)](#loops-laços)
5. [Break e Continue](#break-e-continue)

---

## Estruturas Condicionais

As estruturas condicionais permitem que o código tome decisões baseadas em condições específicas.

### if

A estrutura `if` executa um bloco de código se a condição for verdadeira.

```javascript
let idade = 18;

if (idade >= 18) {
    console.log("Você é maior de idade");
}
```

### if...else

A estrutura `if...else` executa um bloco se a condição for verdadeira e outro bloco se for falsa.

```javascript
let temperatura = 25;

if (temperatura > 30) {
    console.log("Está muito quente!");
} else {
    console.log("A temperatura está agradável");
}
```

### if...else if...else

Permite verificar múltiplas condições em sequência.

```javascript
let nota = 75;

if (nota >= 90) {
    console.log("Excelente! Nota A");
} else if (nota >= 70) {
    console.log("Bom trabalho! Nota B");
} else if (nota >= 50) {
    console.log("Aprovado! Nota C");
} else {
    console.log("Reprovado");
}
```

---

## Operador Ternário

O operador ternário é uma forma concisa de escrever condições simples. A sintaxe é: `condição ? valorSeVerdadeiro : valorSeFalso`

```javascript
let idade = 20;
let status = idade >= 18 ? "Maior de idade" : "Menor de idade";
console.log(status); // "Maior de idade"

// Exemplo com operação
let numero = 15;
let resultado = numero % 2 === 0 ? "Par" : "Ímpar";
console.log(resultado); // "Ímpar"

// Operador ternário aninhado (usar com moderação)
let pontos = 85;
let classificacao = pontos >= 90 ? "Ouro" : pontos >= 70 ? "Prata" : "Bronze";
console.log(classificacao); // "Prata"
```

---

## Switch Case

A estrutura `switch` é útil quando você precisa comparar uma variável com múltiplos valores possíveis.

```javascript
let diaSemana = 3;
let nomeDia;

switch (diaSemana) {
    case 1:
        nomeDia = "Segunda-feira";
        break;
    case 2:
        nomeDia = "Terça-feira";
        break;
    case 3:
        nomeDia = "Quarta-feira";
        break;
    case 4:
        nomeDia = "Quinta-feira";
        break;
    case 5:
        nomeDia = "Sexta-feira";
        break;
    case 6:
        nomeDia = "Sábado";
        break;
    case 7:
        nomeDia = "Domingo";
        break;
    default:
        nomeDia = "Dia inválido";
}

console.log(nomeDia); // "Quarta-feira"
```

### Exemplo com agrupamento de casos

```javascript
let mes = "Janeiro";

switch (mes) {
    case "Dezembro":
    case "Janeiro":
    case "Fevereiro":
        console.log("Verão");
        break;
    case "Março":
    case "Abril":
    case "Maio":
        console.log("Outono");
        break;
    case "Junho":
    case "Julho":
    case "Agosto":
        console.log("Inverno");
        break;
    case "Setembro":
    case "Outubro":
    case "Novembro":
        console.log("Primavera");
        break;
    default:
        console.log("Mês inválido");
}
```

---

## Loops (Laços)

Os loops permitem executar um bloco de código repetidamente.

### Loop for

O loop `for` é usado quando você sabe quantas vezes quer repetir o código.

```javascript
// Contagem de 1 a 5
for (let i = 1; i <= 5; i++) {
    console.log("Número: " + i);
}
// Saída: Número: 1, Número: 2, Número: 3, Número: 4, Número: 5

// Percorrendo um array
let frutas = ["Maçã", "Banana", "Laranja"];
for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
}
// Saída: Maçã, Banana, Laranja

// Contagem regressiva
for (let i = 10; i >= 0; i--) {
    console.log(i);
}
```

### Loop while

O loop `while` executa enquanto a condição for verdadeira. É usado quando não se sabe quantas iterações serão necessárias.

```javascript
let contador = 1;

while (contador <= 5) {
    console.log("Contador: " + contador);
    contador++;
}
// Saída: Contador: 1, Contador: 2, Contador: 3, Contador: 4, Contador: 5

// Exemplo: lendo valores até encontrar um específico
let numero = 0;
while (numero !== 5) {
    console.log("Número atual: " + numero);
    numero++;
}
console.log("Encontrou o 5!");
```

### Loop do...while

O loop `do...while` é similar ao `while`, mas garante que o código seja executado pelo menos uma vez, pois a condição é verificada no final.

```javascript
let i = 1;

do {
    console.log("Valor de i: " + i);
    i++;
} while (i <= 5);
// Saída: Valor de i: 1, Valor de i: 2, Valor de i: 3, Valor de i: 4, Valor de i: 5

// Exemplo: executando ao menos uma vez mesmo com condição falsa
let x = 10;
do {
    console.log("Executou pelo menos uma vez! x = " + x);
} while (x < 5);
// Saída: Executou pelo menos uma vez! x = 10
```

---

## Break e Continue

### Break

O `break` interrompe completamente a execução do loop.

```javascript
// Exemplo 1: Encontrando um número específico
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        console.log("Encontrou o 5! Parando o loop.");
        break;
    }
    console.log(i);
}
// Saída: 1, 2, 3, 4, Encontrou o 5! Parando o loop.

// Exemplo 2: Busca em array
let numeros = [10, 20, 30, 40, 50];
let buscar = 30;

for (let i = 0; i < numeros.length; i++) {
    if (numeros[i] === buscar) {
        console.log("Número " + buscar + " encontrado na posição " + i);
        break;
    }
}
```

### Continue

O `continue` pula a iteração atual e continua com a próxima.

```javascript
// Exemplo 1: Pulando números pares
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        continue; // Pula números pares
    }
    console.log(i);
}
// Saída: 1, 3, 5, 7, 9

// Exemplo 2: Processando apenas valores válidos
let valores = [10, -5, 20, -3, 30, 0, 40];

for (let i = 0; i < valores.length; i++) {
    if (valores[i] <= 0) {
        continue; // Pula valores negativos ou zero
    }
    console.log("Valor positivo: " + valores[i]);
}
// Saída: Valor positivo: 10, Valor positivo: 20, Valor positivo: 30, Valor positivo: 40
```

### Diferença entre Break e Continue

```javascript
console.log("Exemplo com BREAK:");
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        break; // Para o loop completamente
    }
    console.log(i);
}
// Saída: 1, 2

console.log("\nExemplo com CONTINUE:");
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue; // Pula apenas o 3
    }
    console.log(i);
}
// Saída: 1, 2, 4, 5
```

---

## Exercícios Práticos

### Exercício 1: Par ou Ímpar
```javascript
let numero = 7;
if (numero % 2 === 0) {
    console.log(numero + " é par");
} else {
    console.log(numero + " é ímpar");
}
```

### Exercício 2: Tabuada
```javascript
let numeroTabuada = 5;
console.log("Tabuada do " + numeroTabuada + ":");
for (let i = 1; i <= 10; i++) {
    console.log(numeroTabuada + " x " + i + " = " + (numeroTabuada * i));
}
```

### Exercício 3: Somando números positivos
```javascript
let numeros = [5, -3, 8, -1, 10, 2, -7];
let soma = 0;

for (let i = 0; i < numeros.length; i++) {
    if (numeros[i] < 0) {
        continue; // Pula números negativos
    }
    soma += numeros[i];
}

console.log("Soma dos números positivos: " + soma); // 25
```

---

## Resumo

- **if/else**: Executa código baseado em condições
- **Operador Ternário**: Forma concisa de if/else para casos simples
- **Switch**: Compara uma variável com múltiplos valores
- **for**: Loop com contador, ideal quando se sabe o número de iterações
- **while**: Loop que executa enquanto condição for verdadeira
- **do...while**: Similar ao while, mas executa pelo menos uma vez
- **break**: Sai completamente do loop
- **continue**: Pula para a próxima iteração do loop

---

**Dica**: Pratique escrevendo seus próprios exemplos e modificando os códigos acima para entender melhor cada estrutura!
