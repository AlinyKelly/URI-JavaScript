# Resolução da Lista de Exercício 1 - URI Judge Online

**UNIFOR - Universidade de Fortaleza**

**Curso** - Análise e Desenvolvimento de Sistemas 2021.1

**Disciplina** - RACIOCÍNIO LÓGICO E ALGORÍTMICO

**Professor** - Átila Brandão

------------------------------------------------------------------------------------------

[Problema 1000 - Hello World!](https://www.urionlinejudge.com.br/judge/pt/problems/view/1000)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

console.log("Hello World!");

```

[Problema 1001 - Extremamente Básico](https://www.urionlinejudge.com.br/judge/pt/problems/view/1001)

**_Resolução_**

```

```

[Problema 1002 - Área do Círculo](https://www.urionlinejudge.com.br/judge/pt/problems/view/1002)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var pi = 3.14159;
var raio = parseFloat(input);
var area = pi * Math.pow(raio, 2);

console.log("A=" + area.toFixed(4));

```

[Problema 1004 - Produto Simples](https://www.urionlinejudge.com.br/judge/pt/problems/view/1004)

**_Resolução_**

```

```

[Problema 1005 - Média 1](https://www.urionlinejudge.com.br/judge/pt/problems/view/1005)

**_Resolução_**

```

```

[Problema 1006 - Média 2](https://www.urionlinejudge.com.br/judge/pt/problems/view/1006)

**_Resolução_**

```

```

[Problema 1008 - Salário](https://www.urionlinejudge.com.br/judge/pt/problems/view/1008)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var id = lines.shift();
var qtdHorasTrabalhadas = lines.shift();
var valorHora = lines.shift(); // Não precisa converter para Float

var salario = qtdHorasTrabalhadas * valorHora;

console.log("NUMBER = " + id);
console.log("SALARY = U$ " + salario.toFixed(2));

```


[Problema 1010 - Cálculo Simples](https://www.urionlinejudge.com.br/judge/pt/problems/view/1010)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [idItem1, numItem1, valorUnitItem1] = lines.shift().split(" ");
var [idItem2, numItem2, valorUnitItem2] = lines.shift().split(" ");

var valorTotalItem1 = numItem1 * valorUnitItem1;
var valorTotalItem2 = numItem2 * valorUnitItem2;

var valorTotalCompra = valorTotalItem1 + valorTotalItem2;

console.log("VALOR A PAGAR: R$ " + valorTotalCompra.toFixed(2));

```

[Problema 1012 - Área](https://www.urionlinejudge.com.br/judge/pt/problems/view/1012)

**_Resolução_**

```

```

[Problema 1013 - O Maior](https://www.urionlinejudge.com.br/judge/pt/problems/view/1013)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

const [A, B, C] = input.split(" ").map(item => parseInt(item));
const maiorAB = (A + B + Math.abs(A -B)) / 2;
const maiorABC = (C + maiorAB + Math.abs(C - maiorAB)) / 2;
console.log(maiorABC + " eh o maior");

```