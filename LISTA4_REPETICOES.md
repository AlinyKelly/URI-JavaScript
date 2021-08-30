# Resolução da Lista de Exercício 4 - Repetições - URI Judge Online

**UNIFOR - Universidade de Fortaleza**

**Curso** - Análise e Desenvolvimento de Sistemas 2021.1

**Disciplina** - RACIOCÍNIO LÓGICO E ALGORÍTMICO

**Professor** - Átila Brandão

------------------------------------------------------------------------------------------

[Problema 1059 - Números Pares](https://www.urionlinejudge.com.br/judge/pt/problems/view/1059)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

for (var i = 1; i <= 100; i++) {
    if (i % 2 == 0) console.log(i);
}
```

[Problema 1067 - Números Ímpares](https://www.urionlinejudge.com.br/judge/pt/problems/view/1067)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [X] = lines.shift().split(" ").map(item => parseInt(item));
var i;

i = 1;
while(i <= X){
    if(i%2 != 0){
        console.log(i);
    }
    i++;
}
```

[Problema 1070 - Seis Números Ímpares](https://www.urionlinejudge.com.br/judge/pt/problems/view/1070)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [X] = lines.shift().split(" ").map(item => parseInt(item));

var impar;

impar = 0;
while(impar < 6){
    if(X%2 != 0){
        console.log(X);
        impar++;
    }
    X++;
}
```

[Problema 1073 - Quadrado de Pares](https://www.urionlinejudge.com.br/judge/pt/problems/view/1073)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var i;

for(i = 1; i <= N; i++){
    if (i%2 == 0){
        console.log(i + "^2 = " + i*i)
    }
}
```

[Problema 1074 - Par ou Ímpar](https://www.urionlinejudge.com.br/judge/pt/problems/view/1074)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var parity = "";
var signal = "";
var i;

for(i = 0; i < N; i++){
    let [X] = lines.shift().split(" ").map(item => parseInt(item));
   if(X%2==0){
       parity = "EVEN";
   }else{
       parity = "ODD";
   }

   if(X>0){
       signal = "POSITIVE";
   }
   if(X<0){
       signal = "NEGATIVE";
   }

   if(X==0){
       console.log("NULL");
   }else{
       console.log(parity + " " + signal);
   }
}
```

[Problema 1075 - Resto 2](https://www.urionlinejudge.com.br/judge/pt/problems/view/1075)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var i;

for (i=1; i<10000; i++){
    if(i%N == 2){
        console.log(i);
    }
}
```

[Problema 1078 - Tabuada](https://www.urionlinejudge.com.br/judge/pt/problems/view/1078)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var i;

for (i=1; i<=10; i++){
    produto = i * N;
        console.log(i + " x " + N + " = " + produto);
}
```

[Problema 1079 - Médias Ponderadas](https://www.urionlinejudge.com.br/judge/pt/problems/view/1079)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [valor] = lines.shift().split(" ").map(item => parseInt(item));
var i;

for (i=1; i<=valor; i++){
    let [N1, N2, N3] = lines.shift().split(" ").map(item => parseFloat(item));
    let media = ((N1 * 2.0) + (N2 * 3.0) + (N3 * 5.0))/10;
    console.log(media.toFixed(1));    
}
return 0;
```

[Problema 1113 - Crescente e Decrescente](https://www.urionlinejudge.com.br/judge/pt/problems/view/1113)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

do{
    var [X, Y] = lines.shift().split(" ").map(item => parseInt(item));
if(X<Y){
    console.log("Crescente");
}else if (X > Y){
    console.log("Decrescente");
}else if (X == Y){
    break;
}
}while(X!=Y);

return 0;
```

[Problema 1114 - Senha Fixa](https://www.urionlinejudge.com.br/judge/pt/problems/view/1114)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

do{
    var [senha] = lines.shift().split(" ").map(item => parseInt(item));
if(senha == 2002){
    console.log("Acesso Permitido");
}else{
    console.log("Senha Invalida");
}
}while(senha != 2002);

return 0;
```

[Problema 1115 - Quadrante](https://www.urionlinejudge.com.br/judge/pt/problems/view/1115)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

do{
    var [x,y] = lines.shift().split(" ").map(item => parseInt(item));
if(x>0 && y>0){
    console.log("primeiro");
}else if (x<0 && y>0){
    console.log("segundo");
}else if (x<0 && y<0){
    console.log("terceiro");
}else if(x>0 && y<0){
    console.log("quarto");
}else {
    break;
}
}while((x!=0) || (y!=0));

return 0;
```

[Problema 1116 - Dividindo X por Y](https://www.urionlinejudge.com.br/judge/pt/problems/view/1116)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var i;

for (i=1; i<=N; i++){
    let [N1, N2] = lines.shift().split(" ").map(item => parseInt(item));
    if(N2 == 0){
        console.log("divisao impossivel");
    }else {
        let resultado = N1/N2;
        console.log(resultado.toFixed(1));
    }        
}
return 0;
```

[Problema 1117 - Validação de Nota](https://www.urionlinejudge.com.br/judge/pt/problems/view/1117)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var notas = new Array (2);
var i = 0;

while(i <= 1){
    let [nota] = lines.shift().split(" ").map(item => parseFloat(item));

    if(nota < 0 || nota > 10){
        console.log("nota invalida");
    } else if(nota >= 0 && nota <= 10) {
        notas[i++] = nota;       
    }
}
let media = (notas[0] + notas[1]) / 2;
console.log("media = " + media.toFixed(2)); 
```

[Problema 1118 - Várias Notas Com Validação](https://www.urionlinejudge.com.br/judge/pt/problems/view/1118)

Foi respondido em sala pelo professor.
Criar melhorias para o código, reduzi-lo.

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');
var prompt = function(texto) { return lines.shift();};

function validaNota(nota){
    nota = parseFloat(nota);
    if(nota > 10 || nota < 0){
        return true
    } else{
        return false
    }
}

do{
    var nota1 = parseFloat(prompt(""));
    if(validaNota(nota1)){
        console.log("nota invalida");
    }
}while(validaNota(nota1));

do{
    var nota2 = parseFloat(prompt(""));
    if(validaNota(nota2)){
        console.log("nota invalida");
    }
}while(validaNota(nota2));

var media = (nota1 + nota2)/2;
console.log("media = " + media.toFixed(2));

do{
    console.log("novo calculo (1-sim 2-nao)");
    var codigo = prompt("novo calculo (1-sim 2-nao)");
    if(codigo == "1"){
        do{
            var nota1 = parseFloat(prompt(""));
            if(validaNota(nota1)){
                console.log("nota invalida");
            }
        }while(validaNota(nota1));
        
        do{
            var nota2 = parseFloat(prompt(""));
            if(validaNota(nota2)){
                console.log("nota invalida");
            }
        }while(validaNota(nota2));
        
        var media = (nota1 + nota2)/2;
        console.log("media = " + media.toFixed(2));
        
    } else if (codigo=="2"){
        break;
    }
}while(codigo!= 1 || codigo!=2);
```

[Problema 1133 - Resto da Divisão](https://www.urionlinejudge.com.br/judge/pt/problems/view/1133)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var cont;
var [X] = lines.shift().split(" ").map(item => parseInt(item));
var [Y] = lines.shift().split(" ").map(item => parseInt(item));

if(X>Y){
    for(cont=Y+1; cont<X;cont++){
        if(cont%5==2 || cont%5==3){
            console.log(cont);
        }
    }
}else if(X<Y){
    for(cont=X+1; cont<Y;cont++){
        if(cont%5==2 || cont%5==3){
            console.log(cont);
        }
    }
}
```

[Problema 1142 - PUM](https://www.urionlinejudge.com.br/judge/pt/problems/view/1133)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var cont;
var [N] = lines.shift().split(" ").map(item => parseInt(item));

for(cont=1;cont<=N*4;cont+=4){
    console.log(cont + " " + (cont+1) + " " + (cont+2) + " " + "PUM");
    
}
```