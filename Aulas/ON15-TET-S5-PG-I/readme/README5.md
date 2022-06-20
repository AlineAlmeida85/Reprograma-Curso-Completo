## ✔️ `Métodos`
___
### Uma ação do objeto. Eles determinam o comportamento dos objetos de uma classe. Sendo assim, podem alterar o estado de um objeto em determinadas ações.
```javascript
class Pessoa{
  // Abaixo veja um exemplo de como se declarar o constructor com o paramêtro nome. 
  constructor(nome){
    //this está fazendo referência a propriedade da classe Pessoa. 
    this.nome = nome;
  }
  //O método ficará dentro da Classe, pois é um comportamento que ela terá ao ser disparada essa ação no objeto.
  metodo(){
    return alert(`Seja bem vinda, ${this.nome}!`)
  }
}
//O operador new está instanciando a classe Pessoa e atribuindo as suas propriedades ao objeto criado: pessoa1, no caso temos nome. 
const pessoa1 = new Pessoa('Joana')
//O método foi chamado no objeto criado. 
console.log(pessoa1.metodo()) //Seja bem vinda, Joana!
```
