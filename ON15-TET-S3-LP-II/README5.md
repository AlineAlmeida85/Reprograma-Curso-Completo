## ✔️ `Funções` e `Arrow Function`

#### É um bloco de comandos a serem executados quando solicitado, através de uma chamada direta ou em decorrência de um evento; Uma função é o menor bloco de execução/construção no JavaScript, um conjunto de instruções que executa uma tarefa ou calcula um valor; Uma função quando é chamada, pausa a thread (script) para realizar seu processamento, depois retorna o valor final e continua a execução da linha de código na sequência;
___
### Declarando uma função
#### O método mais comum de criar uma função no JS consiste no uso da palavra reservada `function`; Em seguida nomeamos a função, é uma boa prática nomear com verbo para indicar a ação realizada pela função; `()` com a lista de argumentos, caso seja necessário, separados por vírgula; `{}` definição do escopo que recebe a o código que será executado quando a função foi invocada; `return` é a indicação do que a função deve retornar, também interrompendo o a execução do trecho de código em que está inserida;
```javascript
// funcao sem argumentos

  function funcaoUm() {
    return console.log(`retorno da função que não recebe argumentos`)
  }

  // funcao com um único argumento

  function funcaoDois(argumento) {
    return console.log(`retorno da função que recebe um argumentos, neste caso foi ${argumento}`)
  }

  // funcao com mais de um argumento

  function funcaoTres(numeroUm, numeroDois) {
    let soma = numeroUm + numeroDois
    return console.log(`soma = ${soma}`)
  }

  funcaoUm();
  funcaoDois('reprograma');
  funcaoTres(2, 7);

  // funcao anonima

  let funcao4 = function () {
    return console.log('retorno da função anônima')
  } // muito utilizado quando vamos passar a função como parâmetro para outra função

  let soma = function(numero) {return numero * numero};
  console.log(soma(3))
  ```
### Arrow Function
#### Uma sintaxe mais curta e moderna em relação a expressão function e podem substituir em quase todos os casos de forma a diminuir a complexidade de leitura em diversos casos; As arrow functions são geralmente anônimas, mas podem ser nomeadas* ou atribuidas a variáveis para que possam ser invocadas; Estas expressões de funções tem algumas limitações e são melhor utilizadas em funções que não sejam métodos e nem devem ser usadas como construtores;
```javascript
function somar(x, y) {
    return console.log(x + y)
  }

  // sintaxe () => {}
  let somar = (x, y) => console.log(x + y)
  // quando a execução da função ocupa apenas uma linha de código não há neessidade nem do uso do {} e nem do return, simplificando ainda mais a sintaxe
  ```
  #### A sintaxe das arrow functions é bastante comum em padrões funcionais como muito do que aprenderemos em métodos de arrays nas próximas aulas;