## `Passo a Passo Teste da Rota GET`
___



#### Vamos criar testes numa API ja pronta.
<p align="center">
  <img alt="foto" title="foto" src="../img/foto01.png"/>
</p>

#### Essa é a nossa estrutura de projeto. Esta API já está conectada com o banco mas nesta aula vamos focar nos testes. Perceba que, de diferente, temos uma pasta nova, chamada `test` com um arquivo dentro chamado `api.test.js`.
<p align="center">
  <img alt="foto" title="foto" src="../img/foto02.png"/>
</p>

#### Agora vamos criar nosso arquivo `.env`.
```git
    touch .env
```
#### Agora vamos ir no arquivo `.env.example` pra pegar as variáveis obrigatórias que precisamos ter no `.env`.
<p align="center">
  <img alt="foto" title="foto" src="../img/foto03.png"/>
</p>

#### E modificar:
```javascript
    PORT=8000
    MONGODB_URI=mongodb+srv://Aline:Carlos01@cluster0.drwi8.mongodb.net/users
    SECRET=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCn/dUCfUHLoBRIsXhDArKYPXPLrjrEijcoIKoP+M3mzLYefBwxPN8EGXt821P2S+JQMzav8l6ZPAtTz8NluYEji/VsR3XfentcPZxQFgLf+U/myhIFU0natPq4SN37hFrmlHwbwf8w/C5Xzw9jfMNu+Ui76UAsDZFnql5bboYYGwIDAQAB

```
<p align="center">
  <img alt="foto" title="foto" src="../img/foto04.png"/>
</p>

#### Pronto! Vamos então dar o comando:
```git
    npm install 
```
#### Para baixar as dependências do projeto.Agora vamos tentar rodar o projeto pra ver se está realmente tudo ok.
```git
    npm run dev
```
<p align="center">
  <img alt="foto" title="foto" src="../img/foto05.png"/>
</p>

#### Pronto! Tudo conectado e funcionando. Note que temos uma nova dependência instalada, ja deixei no projeto pra focarmos realmente nos testes:
<p align="center">
  <img alt="foto" title="foto" src="../img/foto06.png"/>
</p>

#### Mas para instalar use o comando:
```git
    npm i -D jest supertest
```
#### Vamos prosseguir então. Uma vez que está tuido conectado e funcionando vamos repsrar no nosso script novamente. Antes de chegarmos a aula de teste, nosso script era assim:
<p align="center">
  <img alt="foto" title="foto" src="../img/foto07.png"/>
</p>

#### E agora está assim: 
<p align="center">
  <img alt="foto" title="foto" src="../img/foto08.png"/>
</p>

#### Mudamos pra conseguir usar o `Jest` para testar. Ou seja, se eu digitar o comando:
```git
    npm run test
```
#### Ele vai rodar o `test`. Então vamos abrir outro terminal e rodar o comando acima pra testar:
<p align="center">
  <img alt="foto" title="foto" src="../img/foto09.png"/>
</p>

#### Apresentou erro pois ainda não montamos os códigos de teste mas se percebe que ao chamar `test`, o `jest` é acionado como previsto. Agora vamos importar os pacotes que vamos utilizar dentro do arquivo `app.test.js`.
```javascript
    const request = require("supertest");
```
#### Demos o nome de request pelo fato de ele nos ajudar a simular uma requisição. E vamos requerir também o `app` porque ele é o express, vai permitir nos conectar. 
```javascript
    const app = require("../app");
```
#### Agora vamos chamar a função `describe()` que agrupa um conjunto de testes individuais e que recebe dois parâmetros: uma mensagem e uma função anônima: 
```javascript
    describe("API Test", () => {

});
```
#### Bom, basicamente nossa `API` é um `CRUD` pois temos as rotas de `GET`, `POST`, `PATCH` e `DELETE`, então vamos começar nosso teste pela rota `GET`:
#### 
```javascript
    describe("API Test", () => {
    // agrupa vários testes
    // testar primeiro a rota GET

    test("GET users/all", () => {
        
    })

});
```
#### Chamo o test e passo como parâmetros o verbo seguido do endpoint do verbo e seguido de uma função anônima que vai receber um outro parâmetro que chamamos de `done` que traduzido significa `fim`, vamos chamar le quando terminarmos o teste. Agora vamos criar a conexão com o nosso servidor:
#### 
```javascript
    request(app)
```
#### Chamamos o `supertest` que está armazenado na variável `request` e passo como parâmetro o `app` que é o `express`. 
```javascript
    .get("/users/all")
```
#### E ai eu chamo o verbo e passo o endPoint novamente. Até aqui ja estamos garantindo as boas práticas do meu código pois se mudarem a rota, o teste não vai funcionar. Agora vamos pasar a expectativa do status que esperamos: 
```javascript
    .expect(200)
```
#### E com o código assim:
```javascript
    describe("API Test", () => {
    // agrupa vários testes
    // testar primeiro a rota GET

    test("GET /users/all", (done) => {
        request(app) // aqui acontece a conexão
            .get("/users/all")
            .expect(200)
    })

});
```
#### Já podemos rodar o teste: 
```git
    npm run test
```
#### E...
<p align="center">
  <img alt="foto" title="foto" src="../img/foto10.png"/>
</p>

#### Ele rodou mas apresentou um erro de tempo
```git
 Use jest.setTimeout(newTimeout) to increase the timeout value, if this is a long-running test."
```
#### Continuando... Depois que testamos o status de expectativa de resposta, cmamamos mais uma vez o expect passando uma função anônima com a resposta:
```javascript
    .expect((res) => {
        expect(res.body.length).toBe(0);
    })
```
#### E então, com o código pronto até aqui...
```javascript
    const request = require("supertest");
    const app = require("../app");

    jest.setTimeout(50500);
    jest.useRealTimers();

    describe("API Test", () => {
        // agrupa vários testes
        // testar primeiro a rota GET

        test("GET /users/all", async (done) => {
            await request(app) // aqui acontece a conexão
                .get("/users/all")
                .expect(200)
                .expect((res) => {
                    console.log("BODY DA RESPOSTA:", res.body);
                    expect(res.body.length).toBe(0);
                });
        })

});
```
#### Vamos rodar o teste:
```git
    npm run test
```
#### E...
<p align="center">
  <img alt="foto" title="foto" src="../img/foto11.png"/>
</p>

#### Retornou os dados que estão no meu banco, ou seja, o body da resposta. E depois disso tudo, vamos chamar a função `.end()` passando uma função anonima e como parâmetros passamos o erro e a resposta. Depois de alguns ajustes no código:
```javascript
const request = require("supertest");
const app = require("../app");

// jest.setTimeout(100500);
// jest.useRealTimers();

describe("API Test", () => {
    // agrupa vários testes
    // testar primeiro a rota GET

    test("GET /users/all", (done) => {
        request(app) // aqui acontece a conexão
            .get("/users/all")
            .expect(200)
            .expect((res) => {
                expect(res.body.length).not.toBe(0);
            })
            .end((err, res) => {
                if(err) return done(err);
                return done();
            })
    })

});
```
#### Vamos rodar o teste:
```git
    npm run test
```
#### E...
<p align="center">
  <img alt="foto" title="foto" src="../img/foto12.png"/>
</p>

#### O teste está funcionando. 
<p align="center">
  <img alt="foto" title="foto" src="../img/foto13.png"/>
</p>

#### Vamos analisar o que retornou:
1. Chama o `Jest` para iniciar
2. Imprime a `mensagem do console` de que o `banco foi conectado`
3. Imprime a `mensagem` que foi passada como parâmetro para testar rota e chama a rota que será testada
4. Retorna o `resultado do teste`
5. Retorna o `tempo` que demorou para `executar o teste`


#### Rota testada
