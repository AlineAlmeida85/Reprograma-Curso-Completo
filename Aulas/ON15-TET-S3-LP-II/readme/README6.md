## ✔️ `Objetos`
___
### Um objeto é uma coleção de dados e/ou funcionalidades relacionadas (que geralmente consistem em diversas variáveis e funções — que são chamadas de propriedades e métodos quando estão dentro de objetos). (MDN) Os objetos são formados por chave e valor.

### Criando um objeto:
```javascript
const professora = new Object()
  professora.nome = "Lilit"
  professora.sobrenome = "Bandeira"
  professora.cidade = "São Paulo"

const aluna = {
  nome: { primeiro: "Gabriela", segundo: "Lemos" },
  idade: 20,
  cidade: "São Paulo",
  interesses: ["música", "animes"],
  saudacao: () => console.log("olá meninas"),

};
```
### Acessando o valor de uma propriedade ou método de objetos usando:
#### Notação de ponto - Digitando o ponto, podemos acessar todos as propriedades e métodos encapsuladas dentro do objeto
```javascript
console.log(aluna.nome.primeiro);
aluna.saudacao();
```
#### Notação de cochetes - Usamos as chaves (como strings) para acessar o valor de um item
```javascript
console.log(aluna["nome"]["primeiro"]);
console.log(aluna["idade"]);
console.log(aluna["interesses"][0]);
```
#### Desestruturando um objeto:
```javascript
const { idade, saudacao } = aluna;
```
#### Objeto Date e seus métodos;
#### Cria uma instância JavaScript de Date que representa um único momento no tempo. Objetos Date são baseados no valor de tempo que é o número de milisegundos desde 1º de Janeiro de 1970 (UTC). (MDN)

#### O método toLocaleDateString() retorna uma string com a representação de parte da data baseando-se no idioma. (MDN) Argumentos locales e options
```javascript
const hoje = new Date();

console.log(hoje); // 2022-04-09T10:56:49.693Z

const dia = hoje.getDate();
const mes = hoje.getMonth();
const ano = hoje.getFullYear();

console.log(`${dia}/${mes + 1}/${ano}`); // 09/04/2022 🤔

const dataFormatada = hoje.toLocaleDateString("pt-BR");
console.log(dataFormatada); // 09/04/2022

const options = {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric",
};
const dataLonga = hoje.toLocaleDateString("pt-BR", options);
console.log(dataLonga); // sábado, 9 de abril de 2022
```
