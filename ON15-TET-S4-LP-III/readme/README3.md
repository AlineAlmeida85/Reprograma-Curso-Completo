## ✔️ `Spread/rest`]
___ 
### Spread syntax
#### Sintaxe de Espalhamento permite que um objeto iterável, como uma expressão de array ou uma string seja expandido para ser usado onde zero ou mais argumentos (para chamadas de funções) ou elementos (para arrays literais) são esperados, ou que um objeto seja expandido onde zero ou mais pares propriedade:valor (para objetos literais) são esperados. (MDN)
#### Exemplos de aplicações
```javascript
function imprimir(x, y, z) { 
    return console.log(x, y, z)
}
let argumentos = [2, 3, 5]

espalhar(...argumentos)


let compras = ['calça preta', 'blusa animal print', 'salto fino vermelho 12cm']
let novasCompras = ['argolas grandes de prata', ...compras, 'lace cacheada castanho']
let novissimasCompras = [...compras]

let aluna1 = {nome: 'Jéssica', cidade: 'Recife'}
let aluna2 = {nome: 'Gabriela', cidade: 'São Paulo'}

let alunas = { ...aluna1, ...aluna2 }
```
#### Rest Parameters
#### A sintaxe rest se parece exatamente como a sintaxe de espalhamento, mas esta é usada para desestruturar arrays e objetos. De certa forma, a sintaxe rest é o oposto da sintaxe de espalhamento: A sintaxe de espalhamento (spread) 'expande' um array em vários elementos, enquanto a sintaxe rest coleta multiplos elementos e 'condensa' eles em um único elemento. (MDN)
#### Exemplos de aplicações
```javascript
function imprimirSoma(...argumentos) {
    return argumentos.reduce((previous, current) => previous + current);
}

imprimirSoma(2, 5, 4, 3);
imprimirSoma(1, 8, 4, 5, 6);
```
