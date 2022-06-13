## ✔️ `Objetos`
___
### Um objeto é uma coleção de dados e/ou funcionalidades relacionadas (que geralmente consistem em diversas variáveis e funções — que são chamadas de propriedades e métodos quando estão dentro de objetos). Vamos trabalhar com um exemplo para entender como eles são.

## Classes
### Classe é um conjunto de características e comportamentos que definem o conjunto de objetos pertencentes à essa classe.

#### Antes que a sintaxe da classe estivesse disponível em ES6, se você quisesse fazer POO, seria necessário usar uma função construtora.
```javascript
 function Pessoa (nome) {
     this.nome = nome ;
  }
  var pessoa1 =  new Pessoa ('Joana');
  console.log (pessoa1.nome); // 'Joana'
  ```
#### Isso funcionou bem, até ser necessário que outras classes herdem propriedades e metódos de outra classe.
#### A sintaxe do ES6 é um pouco mais detalhada, mas não tão diferente.
```javascript
class Pessoa{
  constructor(nome){
    this.nome = nome;
  }
}
const pessoa1 = new Pessoa('Joana')
console.log(pessoa1.nome) //'Joana'
```
#### ``Constructor`` Um construtor é uma função que cria uma instância de uma classe que normalmente é chamada de "objeto". Em JavaScript, um construtor é chamado quando você declara um objeto usando a new palavra - chave.
#### O objetivo de um construtor é criar um objeto e definir valores se houver alguma propriedade de objeto presente. É uma maneira elegante de criar um objeto porque você não precisa declarar explicitamente o que retornar, pois a função construtora, por padrão, retorna o objeto que é criado dentro dele.
#### Os parâmetros predefinidos de uma função permitem que parâmetros regulares sejam inicializados com com valores iniciais caso undefined ou nenhum valor seja passado.
```javascript
class Pessoa{
  // Abaixo veja um exemplo de como se declarar o constructor com o paramêtro nome. 
  constructor(nome){
    this.nome = nome;
  }
}
const pessoa1 = new Pessoa('Joana')
console.log(pessoa1.nome) //'Joana'
```
#### ``this`` Em outras palavras, toda função javascript durante a execução tem uma referência ao seu contexto de execução atual, chamado this. Contexto de execução significa a forma que a função é chamada.
```javascript
class Pessoa{
  // Abaixo veja um exemplo de como se declarar o constructor com o paramêtro nome. 
  constructor(nome){
    //this está fazendo referência a propriedade da classe Pessoa. 
    this.nome = nome;
  }
}
const pessoa1 = new Pessoa('Joana')
console.log(pessoa1.nome) //'Joana'
```
#### Objetos Objetos são instâncias de uma classe. Eles podem ser considerados os principais atores de uma aplicação ou simplesmente blocos de construção.
```javascript
class Pessoa{
  // Abaixo veja um exemplo de como se declarar o constructor com o paramêtro nome. 
  constructor(nome){
    //this está fazendo referência a propriedade da classe Pessoa. 
    this.nome = nome;
  }
}
//O operador new está instanciando a classe Pessoa e atribuindo as suas propriedades ao objeto criado: pessoa1, no caso temos nome. 
const pessoa1 = new Pessoa('Joana')
//saída da propriedade nome do objeto pessoa1. 
console.log(pessoa1.nome) //'Joana'
```