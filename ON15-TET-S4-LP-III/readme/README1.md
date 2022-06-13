## ✔️ `Arrays`
___
### Arrays são geralmente descritas como "lista de objetos"; elas são basicamente objetos que contem múltiplos valores armazenados em uma lista. Um objeto array pode ser armazenado em variáveis e ser tratado de forma muito similar a qualquer outro tipo de valor, a diferença está em podermos acessar cada valor dentro da lista individualmente, e fazer super úteis e eficientes coisas com a lista, como laço através da lista e fazer a mesma coisa para cada valor. (MDN)
#### Criando uma array
```javascript
const tipos = ["String", "Números", "Booleanos"];
const cidades = new Array("Recife", "São Paulo", "Manaus");
const cursos = "frontend backend".split(" ");
const tecnologias = Array.of("HTML", "CSS", "JS");
```
#### Acessando o valor de um elemento da array
```javascript
console.log(alunas[1]);
```
#### Desestruturando uma array
```javascript
const [primeiro, segundo] = tipos;
console.log(primeiro);
console.log(segundo);
```