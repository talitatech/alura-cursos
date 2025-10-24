# Calculadora de Média Aritmética (Browser Script)

Branch: `imersaoDevCalculadoraAritmetica`
File: `main.js`

## Overview
Simple browser script computing the arithmetic mean from four bimonthly grades and logging the result.

## Public surface
- Global variables: `nome`, `notaDoPrimeiroBimestre`, `notaDoSegundoBimestre`, `notaDoTerceiroBimestre`, `notaDoQuartoBimestre`, `notaFinal`, `notaFixada`.
- Side effects: writes to console via `console.log`.
- No exported functions. Script executes on load.

## Code
```javascript
var nome = "Talita"

var notaDoPrimeiroBimestre = 9
var notaDoSegundoBimestre = 7
var notaDoTerceiroBimestre = 4
var notaDoQuartoBimestre = 2 

var notaFinal = (notaDoPrimeiroBimestre + notaDoSegundoBimestre + notaDoTerceiroBimestre + notaDoQuartoBimestre) / 4

var notaFixada = notaFinal.toFixed(1)

console.log("Bem vinda " + nome)
console.log(notaFixada)
```

## Usage
Include `main.js` in an HTML page.

```html
<script src="main.js"></script>
```

When the page loads, it logs a welcome message and the computed mean.

## Example Output
```
Bem vinda Talita
5.5
```

## Extending
Refactor to encapsulate logic in a function for reuse:

```javascript
function calcularMedia(n1, n2, n3, n4, casasDecimais = 1) {
  const soma = n1 + n2 + n3 + n4;
  const media = soma / 4;
  return Number(media.toFixed(casasDecimais));
}
```
