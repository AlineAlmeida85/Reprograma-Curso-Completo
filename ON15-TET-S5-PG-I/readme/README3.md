## ✔️ `Arrays`
___
### O array é uma estrutura de dados que contém um índice numérico e um elemento que é o valor.

#### Esse elemento pode ser: uma String - texto, um Numero - float, int, etc, um Objeto, ou até mesmo outro array.

#### Mas porque usar o Array? Quando precisamos montar uma coleção de dados, como por exemplo, uma lista de produtos, nomes, filmes, etc.

#### Como exemplo, vou utilizar uma lista de alunas.
```javascript
let alunas = [
    "Amanda",
    "Priscila",
    "Vanessa"
]
```
#### mas ai precisamos adicionar mais uma alunas.
```javascript
alunas[4] = "Maria"
```
#### Acho que podemos melhorar um pouquinho,
```javascript
alunas[ alunas.length ] = "Maria"
```
#### Seraá que funciona?
```javascript
alunas.push("Maria")
```
#### Aceita uma variavel? Sim, todos os metodos do array aceitam uma variavel, um objeto, um array como parametros, o ideal é sempre manter um padrao da estrutura, se tenho um array de nomes, todos os elemenos do meu array precisam ser nomes.
```javascript
let  jane = "Beatriz"
alunas.push(Jane)
```
#### E quais outros metodos, ou seja, formas de manipula-lo, possui? Exemplo:
```javascript
alunas(array) . metodo
```
#### execulta uma ação caso seja um método, ou mostra um valor, caso seja um atributo. Mostra o tamanho total do array, ou seja, quantos elementos ele tem.
```javascript
let totalDeAlunas = alunas.length
```
#### Criar um Array a partir de uma String
```javascript
let nomes = "Amanda, Priscila, Vanessa";
alunas = nomes.split(",");
```
#### Transformando um Array em String
```javascript
alunas = alunas.join(",");
```
#### Adicionar um elemento ao final do array
```javascript
alunas.push("Maria");
```
#### Remover o ultimo elemento do array e o retorna
```javascript
alunas.pop();
```
#### Adicionar um elemento ao inicio do array
```javascript
alunas.unshift("Bianca");
```
#### Remover o primeiro elemento do array
```javascript
alunas.shift();
```
#### Copiar um array, a gente nunca quer modificar os dados originais, por isso precisamos criar um novo array.
```javascript
var copia = alunas.slice();
```
#### podemos também copiar somente uma parte do array.
```javascript
var copia = alunas.slice(1,3);
```
#### Remover um elemento em uma posição especifica do array
```javascript
alunas.splice(2, 1);
```
#### Acionar um elemento em uma posição especifica do array
```javascript
alunas.splice(2, 0, "Jamile");
```
#### Localizar um indice do Array
```javascript
alunas.indexOf("Beatriz");
```
#### Localizar se um elemento existe no array
```javascript
alunas.includes("Beatriz");
```
#### Ordenar em ordem alfabetica, numerica, etc
```javascript
alunas.sort();
```
#### Inverter a ordem do array
```javascript
alunas.reverse();
```
#### Mergiando 2 arrays, ou seja, unindo os elementos
```javascript
let alunas = ["Amanda", "Priscila", "Vanessa"];
let alunas2 = ["Maria", "Bianca", "Beatriz"];
alunas = alunas.concat(alunas2); // metodo 1 - Array.concat
alunas = [...alunas, ...alunas2]; // metodo 2 - Spread Operator
```



### Outros métodos
| Sintáse     | Descrição  |
| ----------- | -----------|
| array`.forEach`  | `pecorre` um array, sem modificar o array original |
| array`.find`     | `encontra` o primeiro elemento do array especificado e o retorna|
| array`.filter`   | `filtra` todos os elementos e os retorna com base nos parametros especificados|
| array`.map`      | `mapea` um array com base no retorno especificado|
| array`.every`    | returna Bolean `true`, caso todos os elementos sejam iguais|


```javascript	

let alunas = ["Amanda", "Priscila", "Vanessa"];
// Percorre o Array
alunas.forEach( (aluna) => { 
    console.log(aluna);
})
// Faz uma busca 
let busca = "Priscila";
let alunaEncontrada = alunas.find( (aluna) => { 
    return aluna == busca;
})
// Retorna todas as alunas que contem a vogal "a"
let alunasFiltradas = alunas.filter( (aluna) => { 
    return aluna.includes("a");
})
// Deixa todos os nomes em Caixa Alta
let alunasMapeadas = alunas.map( (aluna) => { 
    return aluna.toUpperCase();
})
// Verifica se todas as alunas são iguais
let todasIguais = alunas.every( (aluna) => { 
    return aluna == "Amanda";
})
```
