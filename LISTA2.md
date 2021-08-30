# Resolução da Lista de Exercício 2 - URI Judge Online

**UNIFOR - Universidade de Fortaleza**

**Curso** - Análise e Desenvolvimento de Sistemas 2021.1

**Disciplina** - RACIOCÍNIO LÓGICO E ALGORÍTMICO

**Professor** - Átila Brandão

-------------------------------------------------------------------------------------------


[Problema 1035 - Teste de Seleção 1](https://www.urionlinejudge.com.br/judge/pt/problems/view/1035)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');

const [A, B, C, D] = input.split(" ").map(item => parseInt(item));

if (B > C && D > A && C + D > A + B && C > 0 && D > 0 && A % 2 == 0) {
	console.log("Valores aceitos");
} else {
	console.log("Valores nao aceitos");
}
```

[Problema 1036 - Fórmula de Bhaskara](https://www.urionlinejudge.com.br/judge/pt/problems/view/1036)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [A, B, C] = input.split(" ").map(item => parseFloat(item));
var delta = (B * B) - 4 * A * C;

if (delta < 0 || A == 0) {
	console.log("Impossivel calcular");
} else {
	const X1 = ( -B + Math.sqrt(delta)) / (2 * A);
	const X2 = ( -B - Math.sqrt(delta)) / (2 * A);

	console.log("R1 = " + X1.toFixed(5));
	console.log("R2 = " + X2.toFixed(5));
}
```

[Problema 1037 - Intervalo](https://www.urionlinejudge.com.br/judge/pt/problems/view/1037)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');

const [valor] = input.split(" ").map(item => parseFloat(item));

if (valor < 0 || valor > 100) {
        console.log("Fora de intervalo");
    }
    else if (valor >= 0 && valor <= 25) {
        console.log("Intervalo [0,25]");
    }
    else if (valor > 25 && valor <= 50) {
        console.log("Intervalo (25,50]");
    }
    else if (valor > 50 && valor <= 75) {
        console.log("Intervalo (50,75]");
    }    
    else if (valor > 75 && valor <= 100) {
        console.log("Intervalo (75,100]");
    }        
    return 0;
```

[Problema 1038 - Lanche](https://www.urionlinejudge.com.br/judge/pt/problems/view/1038)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');

const [cod, quant] = input.split(" ").map(item => parseInt(item));

if(cod == 1){
	console.log("Total: R$ " + parseFloat(4.00*quant).toFixed(2));
} else if (cod == 2){
	console.log("Total: R$ " + parseFloat(4.50*quant).toFixed(2));
} else if (cod == 3){
	console.log("Total: R$ " + parseFloat(5.00*quant).toFixed(2));
} else if (cod == 4){
	console.log("Total: R$ " + parseFloat(2.00*quant).toFixed(2));
} else if (cod == 5){
	console.log("Total: R$ " + parseFloat(1.50*quant).toFixed(2));

	return 0;
}
```

[Problema 1040 - Média 3](https://www.urionlinejudge.com.br/judge/pt/problems/view/1040)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [N1, N2, N3, N4] = lines.shift().split(" ").map(item => parseFloat(item));

var media = ((N1*2) + (N2*3) + (N3*4) + (N4*1)) / 10;
console.log("Media: " + media.toFixed(1));

if (media >= 7.0){
    console.log("Aluno aprovado.");

} else if (media >= 5.0 && media <= 6.9){
    console.log("Aluno em exame.");

    let [N5] = lines.shift().split(" ").map(item => parseFloat(item));

    console.log("Nota do exame: " + N5.toFixed(1));

    media = (media + N5) / 2;

    if (media >= 5.0){
        console.log("Aluno aprovado.");
    } else {
        console.log("Aluno reprovado.");
    }

    console.log("Media final: " + media.toFixed(1));
    
} else {
    console.log("Aluno reprovado.");
}
```

[Problema 1041 - Coordenadas de um Ponto](https://www.urionlinejudge.com.br/judge/pt/problems/view/1041)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [x, y] = lines.shift().split(" ").map(item => parseFloat(item));

if(x == 0 && y == 0){
    console.log("Origem");
}else if(x == 0){
    console.log("Eixo Y");
}else if(y == 0){
    console.log("Eixo X");
}else if(x > 0 && y > 0){
    console.log("Q1");
}else if(x > 0 && y < 0){
    console.log("Q4");
}else if(x < 0 && y > 0){
    console.log("Q2");
}else{
    console.log("Q3");
}

return 0;
```

[Problema 1045 - Tipode de Triângulos](https://www.urionlinejudge.com.br/judge/pt/problems/view/1045)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [A, B, C] = lines.shift().split(" ").map(item => parseFloat(item));

var ladoA = Math.max(A, Math.max(B, C));
var ladoB = 0;
var ladoC = 0;

        if (ladoA == A) {
            ladoB = Math.max(B, C);
            ladoC = Math.min(B, C);
        }
        if (ladoA == B) {
            ladoB = Math.max(A, C);
            ladoC = Math.min(A, C);
        }
        if (ladoA == C) {
            ladoB = Math.max(B, A);
            ladoC = Math.min(B, A);
        }
        
        if (ladoA >= (ladoB + ladoC)) {
            console.log("NAO FORMA TRIANGULO");

        } else if (ladoA * ladoA > ((ladoB * ladoB) + (ladoC * ladoC))) {
            console.log("TRIANGULO OBTUSANGULO");
        }
        if (ladoA * ladoA == ((ladoB * ladoB) + (ladoC * ladoC))) {
            console.log("TRIANGULO RETANGULO");
        }

        if (ladoA * ladoA < ((ladoB * ladoB) + (ladoC * ladoC))) {
            console.log("TRIANGULO ACUTANGULO");
        }
        if ((ladoA == ladoB) && (ladoA == ladoC)) {
            console.log("TRIANGULO EQUILATERO");
        }
        if (((ladoA == ladoB) && (ladoA != ladoC)) || ((ladoA == ladoC) && (ladoA != ladoB)) || ((ladoB == ladoC) && (ladoB != ladoA))) {
            console.log("TRIANGULO ISOSCELES");
        }
```

[Problema 1048 - Aumento de Salário](https://www.urionlinejudge.com.br/judge/pt/problems/view/1048)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [salario] = lines.shift().split(" ").map(item => parseFloat(item));
var novoSal = 0.00;
var reajuste = 0.00;

if (salario >= 0.00 && salario <= 400.00){
    novoSal = salario + (salario * 0.15);
    reajuste = (salario * 0.15);
    console.log("Novo salario: " + novoSal.toFixed(2));
    console.log("Reajuste ganho: " + reajuste.toFixed(2));
    console.log("Em percentual: 15 %");
}else if (salario >= 400.01 && salario <= 800.00){
    novoSal = salario + (salario * 0.12);
    reajuste = (salario * 0.12);
    console.log("Novo salario: " + novoSal.toFixed(2));
    console.log("Reajuste ganho: " + reajuste.toFixed(2));
    console.log("Em percentual: 12 %");
}else if (salario >= 800.01 && salario <= 1200.00){
    novoSal = salario + (salario * 0.10);
    reajuste = (salario * 0.10);
    console.log("Novo salario: " + novoSal.toFixed(2));
    console.log("Reajuste ganho: " + reajuste.toFixed(2));
    console.log("Em percentual: 10 %");
}else if (salario >= 1200.01 && salario <= 2000.00){
    novoSal = salario + (salario * 0.07);
    reajuste = (salario * 0.07);
    console.log("Novo salario: " + novoSal.toFixed(2));
    console.log("Reajuste ganho: " + reajuste.toFixed(2));
    console.log("Em percentual: 7 %");
}else if (salario >= 2000.01){
    novoSal = salario + (salario * 0.04);
    reajuste = (salario * 0.04);
    console.log("Novo salario: " + novoSal.toFixed(2));
    console.log("Reajuste ganho: " + reajuste.toFixed(2));
    console.log("Em percentual: 4 %");
}
```

[Problema 1051 - Imposto de Renda](https://www.urionlinejudge.com.br/judge/pt/problems/view/1051)

**_Resolução_**

```
var input = require('fs').readFileSync('/dev/stdin', 'utf8');
var lines = input.split('\n');

var [salario] = lines.shift().split(" ").map(item => parseFloat(item));
var imposto = 0.00;
var taxa1, taxa2, taxa3 = 0.00;

        if (salario <= 2000) {
            console.log("Isento");
        } else {
            if (salario > 2000 && salario <= 3000) {
                taxa1 = salario - 2000;
                taxa1 = ((taxa1 * 8) / 100);
                imposto = taxa1;
            } else if (salario > 3000 && salario <= 4500) {
                taxa1 = salario - 2000;
                taxa2 = taxa1 - 1000;
                taxa1 -= taxa2;
                taxa1 = ((taxa1 * 8) / 100);
                taxa2 = ((taxa2 * 18) / 100);
                imposto = taxa2 + taxa1;
            } else {
                taxa1 = salario - 2000;
                taxa2 = taxa1 - 1000;
                taxa3 = taxa2 - 1500;
                taxa1 -= taxa2;
                taxa2 -= taxa3;
                taxa1 = ((taxa1 * 8) / 100);
                taxa2 = ((taxa2 * 18) / 100);
                taxa3 = ((taxa3 * 28) / 100);
                imposto = taxa3 + taxa2 + taxa1;
            }
            console.log("R$ " + imposto.toFixed(2));
        }
```