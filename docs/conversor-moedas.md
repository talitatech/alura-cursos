# Conversor de Moedas (Browser Function)

Branch: `imersaoDevConversorMoedas`
File: `main.js`

## Overview
Provides a single public function `Converter()` that reads a numeric value (USD) from an input field with id `valor`, converts it to BRL at a fixed rate, and renders the result into an element with id `valorConvertido`.

## Public API
### `Converter()`
- **Parameters**: none
- **Returns**: void
- **Side effects**:
  - Reads `#valor` input value
  - Writes text into `#valorConvertido`
  - Logs converted value to console

#### Implementation
```javascript
function Converter() {
  var valorElemento = document.getElementById("valor");
  var valor = valorElemento.value;
  var valorEmDolarNumerico = parseFloat(valor);

  var valorEmReal = valorEmDolarNumerico * 5;
  console.log(valorEmReal);
  var elementoValorConvertido = document.getElementById("valorConvertido");
  var valorConvertido = "O resultado em real é R$ " + valorEmReal;
  elementoValorConvertido.innerHTML = valorConvertido;
}
```

## Usage
Include `index.html`, `style.css`, and `main.js` from the branch. The HTML binds the button click to `Converter()`.

```html
<label for="moeda">Insira o valor</label>
<input type="number" id="valor" />
<button type="submit" onclick="Converter()">Converter</button>
<h2 id="valorConvertido"></h2>
```

## Examples
- **Input**: 10 (interpreted as USD)
- **Output text**: `O resultado em real é R$ 50`

## Notes
- The conversion rate is hardcoded as `5`. For production, consider fetching live rates and formatting currency using `Intl.NumberFormat`.
