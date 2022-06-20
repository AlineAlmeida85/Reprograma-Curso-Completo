## ✔️ `Métodos de Arrays`
___
### Array para exemplos:
```javascript
const numeros = [3, 2, 4, 3, 5, 1, 3, 4, 2];
find()

const encontrarPrimeiro = numeros.find((element) => element == 2);
console.log(encontrarPrimeiro); // retorno 2
filter()

const filtrarPor = numeros.filter((element) => element == 3);
console.log(filtrarPor); // retorno [3, 3, 3]
map()

const executarTodos = numeros.map((element) => (element = 4));
console.log(executarTodos); // retorn  [4, 4, 4, 4, 4, 4, 4, 4, 4]
forEach()

const verTodos = numeros.forEach((element) => console.log(element));
console.log(verTodos); // retorno  3\n2\n4\n3\n5\n1\n3\n4\n2
```
#### reduce() -> O método reduce() uma callback que será executada para cada elemento da array, resultando num único valor de retorno, esta callback pode receber alguns parâmetros, sendo os mais comuns o acumulador e o valorAtual
```javascript
const ReduzirPara = numeros.reduce(
  (acumulador, valorAtual) => acumulador + valorAtual
);
console.log(ReduzirPara); // retorno 27
concat() -> retorna um novo array contendo todos os arrays ou valores passados como parâmetro. (MDN)

const arrayConcatenada = numeros.concat(1, [2, 3], "café");
console.log(arrayConcatenada); // retorno [3, 2, 4, 3, 5, 1, 3, 4, 2, 1, 4, 5, 2, 'café']
```
#### push(): -> adiciona um ou mais elementos ao final de um array e retorna o novo comprimento desse array. (MDN)
#### const adicionaNoFinal = numeros.push(2, 3);
console.log(adicionaNoFinal); // retorno 11
pop(): -> remove o último elemento de um array e retorna aquele elemento. (MDN)
```javascript
const removeUltimo = numeros.pop();
console.log(removeUltimo); // retorno 2
```
#### shift() -> remove o primeiro elemento de um array e retorna esse elemento. Este método muda o tamanho do array. (MDN)
```javascript
const removePrimeiro = numeros.shift();
console.log(removeUltimo); // retorno 3
```
#### unshift() -> adiciona um ou mais elementos no início de um array e retorna o número de elementos (propriedade length) atualizado. (MDN)
```javascript
const adicionaNoInicio = numeros.unshift(4, 1);
console.log(adicionaNoFinal); // retorno 11
```
#### slice() -> retorna uma cópia de parte de um array a partir de um subarray criado entre as posições início e fim (fim não é necessário) de um array original. O Array original não é modificado. (MDN)
```javascript
const copiaParte = numeros.slice(2, 5);
console.log(copiaParte); //retorno [4, 3, 5]
```
#### splice() -> altera o conteúdo de uma lista, adicionando novos elementos enquanto remove elementos antigos. (MDN)
```javascript
const removeEAdiciona = numeros.splice(2, 2, "novo");
console.log(removeEAdiciona); //retorno [4, 3] -> removidos
console.log(numeros); // retorno [3, 2, 'novo', 5, 1, 3, 4, 2]
```
#### indexOf() -> retorna o primeiro índice em que o elemento pode ser encontrado no array, retorna -1 caso o mesmo não esteja presente. (MDN)
```javascript
const localizaElemento = numeros.indexOf(2);
console.log(localizaElemento); // retorno 1
```
#### includes() -> determina se um array contém um determinado elemento, retornando true ou false apropriadamente. (MDN)
```javascript
const verificaSeExiste = numeros.includes(4);
console.log(localizaElemento); // true
```
#### join() -> junta todos os elementos de um array em uma string e retorna esta string. (MDN)
```javascript
const transformaString = numeros.join("-");
console.log(transformaString); // retorno "3, 2, 4, 3, 5, 1, 3, 4, 2"