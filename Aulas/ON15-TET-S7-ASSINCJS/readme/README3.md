## ✔️ `Promises` 
___
### Promise é um objeto do JavaScript que tem a função de lidar com assincronicidade através de estados;
### Funções assíncronas modernas retornam uma promise que representa a eventual falha ou conclusão de uma operação assíncrona, assim uma função assíncrona retorna um valor como uma função síncrona, porém no lugar do valor final, retorna uma promessa ao valor em algum momento no futuro;
#### Ciclo de vida da Promisse (estados):
| Estado    | Significado                                    |
|---------- | ---------------------------------------------- |
| Pending   | Estado inicial, quando a promise ainda está em execução (não resolveu ou rejeitou)                          |
| Fulfilled | Quando executou todas as operações com sucesso |
| Rejected  | Quando a execução finalizou com erro, falhou   |
| Settled   | ome genérico para estado final de executado, independente de ter retornado sucesso ou erro                |

```javascript
// promisse
function promessa() {
    return new Promisse((resolve, reject) => {
        setTimeout((error) => {
            if(error) {
                return reject(new Error('deu erro!'))
            }
            return resolve("sucesso!")
        }, 3000)
    })
}

const resultado = promessa()
resultado.then(resultado => {
    console.log(resultado)
}).catch(error => {
    console.log(error)
})
```
#### Cria-se uma promise a partir da função construtora Promise passando como argumento uma callback que por sua vez recebe como argumentos os dois resultados possíveis para a promise: resolve ou rejeit, duas outras funções que executam o possível sucesso ou erro da promessa, respectivamente;
#### - `resolve()`: Função que executa caso a promise seja resolvida;
#### - `reject()`: Função que executa caso a promise seja rejeitada;
#### Resolvemos as promises através de métodos próprios, que chamam as callbacks depois da conclusão da promise;
#### - `then()`: Método que ativa uma callback quando a promise for resolvida, o argumento desta callback é sempre o valor retornado na função `resolve()`;
####  - `then()`: retorna uma nova promise e por isso vários thens podem ser encadeados para casos onde existam duas ou mais operações assíncronas consecutivas, neste caso o valor do primeiro argumento de cada then encadeado será o valor do retorno do anterior;
#### `catch()`: Método que ativa uma callback quando a promise for rejeitada, o argumento desta callback é sempre o valor retornado na `reject()`;
#### `finally()`: Método que ativa uma callback quando a promisse acabar, independente de ter sido resolvida ou rejeitada, não recebe como argumento o retorno de `resolve()` ou `reject()`;
