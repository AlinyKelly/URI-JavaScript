# Resolução da Lista de Exercício 3 (Avaliativa)- URI Judge Online

**UNIFOR - Universidade de Fortaleza**

**Curso** - Análise e Desenvolvimento de Sistemas 2021.1

**Disciplina** - RACIOCÍNIO LÓGICO E ALGORÍTMICO

**Professor** - Átila Brandão

------------------------------------------------------------------------------------------

[Problema 1042 - Sort Simples](https://www.urionlinejudge.com.br/judge/pt/problems/view/1042)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [valor1, valor2, valor3] = lines.shift().split(" ").map(item => parseInt(item));

if((valor1 < valor2) && (valor2 < valor3)){
    console.log(valor1);
    console.log(valor2);
    console.log(valor3);

} else if ((valor1 < valor3) && (valor3 < valor2)) {
    console.log(valor1);
    console.log(valor3);
    console.log(valor2);

} else if ((valor2 < valor1) && (valor1 < valor3)){
    console.log(valor2);
    console.log(valor1);
    console.log(valor3);

} else if ((valor2 < valor3) && (valor3 < valor1)){
    console.log(valor2);
    console.log(valor3);
    console.log(valor1);

} else if ((valor3 < valor1) && (valor1 < valor2)){
    console.log(valor3);
    console.log(valor1);
    console.log(valor2);

} else {
    console.log(valor3);
    console.log(valor2);
    console.log(valor1);
}

    console.log("\n" + valor1);
    console.log(valor2);
    console.log(valor3);
```


[Problema 1043 - Triângulos](https://www.urionlinejudge.com.br/judge/pt/problems/view/1043)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');


var [A, B, C] = lines.shift().split(" ").map(item => parseFloat(item));

if ((C < A+B) && (A < B+C) && (B < A+C)) {
    console.log("Perimetro = " + (A + B + C).toFixed(1));
}
else {
    console.log("Area = " + (((A + B) * C)/2).toFixed(1));
}
```


[Problema 1044 - Múltiplos](https://www.urionlinejudge.com.br/judge/pt/problems/view/1044)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [A, B] = lines.shift().split(" ").map(item => parseFloat(item));

if ((A%B == 0) || (B%A == 0)){
    console.log("Sao Multiplos");
} else {
    console.log("Nao sao Multiplos");
}
```


[Problema 1046 - Tempo de jogo](https://www.urionlinejudge.com.br/judge/pt/problems/view/1046)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [horaInicial, horaFinal] = input.split(" ").map(v => parseInt(v));

var tempoInicial = horaInicial*3600;
var tempoFinal = horaFinal*3600;

if(tempoInicial >= tempoFinal){
    tempoFinal += 24*3600;
}

var deltaTempo = tempoFinal - tempoInicial;
var deltaHora = parseInt(deltaTempo/3600);

console.log("O JOGO DUROU " + deltaHora + " HORA(S)");
```


[Problema 1047 - Tempo de jogo minutos](https://www.urionlinejudge.com.br/judge/pt/problems/view/1047)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');
var prompt = function(texto) { return lines.shift();};

var input = prompt();
var [horaInicial, minutoInicial, horaFinal, minutoFinal] = input.split(" ").map(v => parseInt(v));

var tempoInicial = horaInicial*3600 + minutoInicial*60;
var tempoFinal = horaFinal*3600 + minutoFinal*60;

if(tempoInicial >= tempoFinal){
    tempoFinal += 24*3600;
}

var deltaTempo = tempoFinal - tempoInicial;
var deltaMinuto = parseInt(deltaTempo/60)%60;
var deltaHora = parseInt(deltaTempo/3600)%(deltaMinuto > 0? 24:25);

console.log("O JOGO DUROU " + deltaHora + " HORA(S) E " + deltaMinuto + " MINUTO(S)");

```


[Problema 1049 - Animal](https://www.urionlinejudge.com.br/judge/pt/problems/view/1049)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');
var prompt = function(texto) { return lines.shift();};

const pA = prompt("A");
const pB = prompt("B");
const pC = prompt("C");

if (pA[0] == 'v'){
    if(pB[0] == 'a'){
        if(pC[0] == 'c')console.log("aguia");
        else console.log("pomba");
    }else{
        if(pC[0] == 'o')console.log("homem");
        else console.log("vaca");
    }
}else{
    if(pB[0] == 'i'){
        if(pC[2] == 'm')console.log("pulga");
        else console.log("lagarta");
    }else{
        if(pC[0] == 'h')console.log("sanguessuga");
        else console.log("minhoca");
    }
}
```


[Problema 1050 - DDD](https://www.urionlinejudge.com.br/judge/pt/problems/view/1050)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [DDD] = lines.shift().split(" ").map(item => parseFloat(item));

if (DDD == 61){
    console.log("Brasilia");
} else if (DDD == 71){
    console.log("Salvador");
} else if (DDD == 11){
    console.log("Sao Paulo");
} else if (DDD == 21){
    console.log("Rio de Janeiro");
} else if (DDD == 32){
    console.log("Juiz de Fora");
} else if (DDD == 19){
    console.log("Campinas");
} else if (DDD == 27){
    console.log("Vitoria");
} else if (DDD == 31){
    console.log("Belo Horizonte")
} else {
    console.log("DDD nao cadastrado");
}

return 0;
```

[Problema 1052 - Mês](https://www.urionlinejudge.com.br/judge/pt/problems/view/1052)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [mes] = lines.shift().split(" ").map(item => parseInt(item));

if (mes == 1){
    console.log("January");
} else if (mes == 2){
    console.log("February");
} else if (mes == 3){
    console.log("March");
} else if (mes == 4){
    console.log("April");
} else if (mes == 5){
    console.log("May");
} else if (mes == 6){
    console.log("June");
} else if (mes == 7){
    console.log("July");
} else if (mes == 8){
    console.log("August")
} else if (mes == 9){
    console.log("September");
} else if (mes == 10){
    console.log("October");
} else if (mes == 11){
    console.log("November");
} else if (mes == 12){
    console.log("December");
}
return 0;
```