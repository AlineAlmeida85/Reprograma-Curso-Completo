## ✔️ `async/await` 
___
#### As palavra-chaves `async` e `await` atuam como um '`açúcar sintático`' em cima de promises, faciltando a visualização e tornando a leitura do código assíncrono mais próxima do código síncrono;
#### Toda função que recebe o `async` se torna uma função assíncrona, que passa a retornar uma promise ao invés de retornar um valor diretamente, como uma promise o retorno desta função pode ser tratado com um `then()` normalmente;
#### Uma função assíncrona espera a possibilidade de a palavra-chave `await` ser usada para invocar código assíncrono;
#### `await` indica que o JavaScript deve esperar o retorno de uma promise para continuar a execução, importante usar apenas quando necessário tratar respostas de uma promise para não paralizar o fluxo, quando usado da maneira correta não altera a performance da aplicação;
#### O `await` só funciona dentro de funções assíncronas e é colocada na frente de qualquer função que retorne promise para pausar o código até que a promise seja resolvida, retornando o valor resultante;
#### Não precisa de funções para sincronizar os resultados;
#### Outro método importante da promise é o `Promisse.all()` que recebe uma array de funções assincronas independentes entre si, evitando o uso de awaits que não sejam necessários;
#### Facilita o tratamento de erros seja com menor encadeamento do `.then()` ou ainda com o uso de `try/catch`;
```javascript
function transformarDiasEmHoras(dias) {
    return new Promisse(resolve => {
        setTimeout(() => {
            resolve(dias * 24)
        }, 1000)
    })
}
function transformarHorasEmMinutos(horas) {
    return new Promisse(resolve => {
        setTimeout(() => {
            resolve(horas * 60)
        }, 1000)
    })
}
async function transformarDiasEmMinutos(dias) {
    try {
        const horas = await transformarDiasEmHoras(dias)
        const minutos = await transformarHorasEmMinutos(horas)
            return console.log(horas, minutos)
        }
        catch(error){
            console.log(error)
        }
    }
```
### `try/catch`
#### É usado para marcar um bloco que será testado (`try`) e especifica uma ação para que uma possível exceção(erro) seja capturada(`catch`);
#### Ao usar o `try` é criado um bloco de código protegido, que caso ocorra algum erro neste bloco, a execução é desviada para o `catch()`, desta forma a aplicação não será quebrada e o erro poderá ser tratado e o código segue sua execução;
#### O `catch()` é executado somente quando há alguma exceção no bloco `try`, caso contrário ele será ignorado, o argumento recebido pelo `catch` é a exceção ocorrida no bloco `try` e costuma ser chamada de err/error;