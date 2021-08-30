# LISTA DE EXERCÍCIOS AV2 - AVALIATIVO - URI Judge Online

**UNIFOR - Universidade de Fortaleza**

**Curso** - Análise e Desenvolvimento de Sistemas 2021.1

**Disciplina** - RACIOCÍNIO LÓGICO E ALGORÍTMICO

**Professor** - Átila Brandão

------------------------------------------------------------------------------------------

[Problema 1101 - Sequência de números e soma](https://www.urionlinejudge.com.br/judge/pt/problems/view/1101)

**_Resolução_** 
**Wrong answer 10%**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var soma = 0;
var auxiliar;

while (true){
    var [N, M] = lines.shift().split(" ").map(item => parseInt(item));
    if(N<=0 || M<=0){
        break;
    } else {
        auxiliar = 0;
        if(N<M){
            for(auxiliar = N; auxiliar<=M; auxiliar++){
                console.log(auxiliar);
                soma+=auxiliar;
            }
            console.log("Sum="+ soma);
        } else if (N > M){
            soma = 0;
            for(auxiliar = M; auxiliar<=N; auxiliar++){
                console.log(auxiliar);
                soma+=auxiliar;
            }
            console.log("Sum=" + soma);
        }
    }
}
return 0;
```

**Código Aceito**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N, M] = lines.shift().split(" ").map(item => parseInt(item));

while(M > 0 && N > 0){
    var auxiliar = 0;
    var soma = 0;
    var i = 0;
    var arrayLista = [];

    if(N < M){
        auxiliar = M;
        M = N;
        N = auxiliar;
    }

    for ( i = M; i <= N; i++){
        soma += i;
        arrayLista.push(i);
    }
    console.log(arrayLista.join(" ") + " " + "Sum=" + soma);
    soma = 0;
    var [N, M] = lines.shift().split(" ").map(item => parseInt(item));   
}
```

[Problema 1160 - Crescimento populacional](https://www.urionlinejudge.com.br/judge/pt/problems/view/1160)

**_Resolução_**
**Wrong aswer 10%**
```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [T] = lines.shift().split(" ").map(item => parseInt(item));

for (var i = 1; i<=T;i++){
    let [PA, PB, G1, G2] = lines.shift().split(" ").map(item => parseFloat(item));
    PA = parseInt(PA);
    PB = parseInt(PB);
    var anos = 0;

    while(PA < PB){
        anos++;   
        PA = PA + (PA*G1)/100);
        PB = PB + (PB*G2)/100);

        if ((PA >PB) || anos > 100){            
            break;
        }
    }
    if(anos <= 100){
        console.log(anos + " anos.");
    } else {
        console.log("Mais de 1 seculo.");
    }    
}
```

**Código Aceito**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [T] = lines.shift().split(" ").map(item => parseInt(item));
var anos;
for (var i = 0; i<T;i++){
    let [PA, PB, G1, G2] = lines.shift().split(" ").map(item => parseFloat(item));
    
    for (anos = 0; PA <= PB; anos++){
    
        PA += (PA*G1)/100;
        PB += (PB*G2)/100;

        PA = parseInt(PA);
        PB = parseInt(PB);

        if (anos > 100){            
            break;
        }
    }
    if(anos <= 100){
        console.log(anos + " anos.");
    } else {
        console.log("Mais de 1 seculo.");
    }    
}
```

[Problema 2718 - Luzes de Natal](https://www.urionlinejudge.com.br/judge/pt/problems/view/2718)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N] = lines.shift().split(" ").map(item => parseInt(item));
var cont = 0;
for (let i = 0; i < N; i++){
    let [X] = lines.shift().split(" ").map(item => parseInt(item));

    let converterDecimal = X.toString(2);
    let arrayBinario = converterDecimal.split('').join('');

    var tamBinario = arrayBinario.length;
    var totLampadas = 0;
    for (let i = 0; i<tamBinario; i++){
        if(arrayBinario[i] == "1"){
            cont++;
        } else {
            cont = 0;
        }

        if(totLampadas<cont){
            totLampadas = cont;
        }
    }
    console.log(totLampadas);
    arrayBinario = "";
    cont = 0;    
}
```

[Problema 2867 - Dígitos](https://www.urionlinejudge.com.br/judge/pt/problems/view/2867)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [C] = lines.shift().split(" ").map(item => parseInt(item));

for (var i = 1; i<=C;i++){
    let [N, M] = lines.shift().split(" ").map(item => parseInt(item));
    
    let contagem = Math.floor(Math.log10(Math.pow(N, M))+1);
    console.log(contagem);
}

```
