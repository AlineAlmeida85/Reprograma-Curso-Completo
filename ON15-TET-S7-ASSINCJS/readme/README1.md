## ✔️ `Ciclo de vida das aplicações JavaScript`

___
### `Funções `são o menor bloco de execução no `JavaScript`, um conjunto de instruções que executa uma tarefa ou calcula um valor;
### `Funções síncronas`: São funções que, quando chamadas, pausam a thread principal (script) para realizar seu processamento, depois retorna o valor final e continua a execução da linha de código na sequência;
#### Exemplo:
```javascript
// function
function somar(numero) {
    return numero + numero
}
```
#### Ou
```javascript
// arrow function
soma = (numero) => {
    return numero + numero
}
```
___
### `Funções assíncronas`: Cria uma thread paralela, que será executada em segundo plano sem interromper o fluxo principal, logo toda função que depende de alguma execução externa e/ou possuem timer para retornarem, são executadas em background e ao fim serão retornadas através do Event Loop, tornando possível a continuação do fluxo da aplicação já que não trava o script (thread principal);
```javascript
// função assíncrona
function subtrair(num1, num2) {
    setTimeout(() => {
        return num1 - num2
    }, 1000)    
}
```
#### A ordem com que seu código é escrito é diferente da ordem em que é executado;
#### Logo é muito importante resolver de forma adequada a ordem com que seu código é executado para evitar problemas;
- `setTimeout()`: É uma função do JavaScript que executa um bloco de código assíncronamente depois de um dado período de tempo, essa função recebe dois parâmetros, sendo o primeiro uma função callback e o segundo um intervalo de tempo em milissegundos (1000ms = 1s)
#### `Event Loop`: A fila de eventos (Event Loop) é responsável por enviar novas funções que foram resolvidas de forma assíncrona para a trilha principal de processamento (Call Stack), seguindo a estrutura de dados da fila (Callback Queue) assim mantendo a sequência correta de execução dos eventos/funções;