## `Meu Primeiro Teste` com Jest
___

### `Testes Unitários`
#### O teste unitário avalia uma pequena porção de código, método ou função que retorne, explicitamente, um objeto, valor ou retorno programado na expectativa que aquele trecho de código demanda. Faz mais sentido ainda se, neste contexto, estivermos trabalhando com Clean Code, em que cada método é escrito de forma curta e direcionada para solucionar uma única questão.
#### Para realizar o teste de unidade você deve obrigatoriamente ter acesso ao código que está sendo testado. Esse tipo de teste geralmente é elaborado pelo desenvolvedor que escreveu o código.

___
## `Jest e Supertest`

### `Supertest`
#### Supertest é um módulo que forja requisições visando testar webservers em Node. js e verifica o retorno das mesmas para automatizar testes deste tipo de infraestrutura, principalmente web APIs.
### **Instalando dependências**
```git
npm i express

npm i -D jest supertest
```
#### **Atualizando scripts**
```javascript
    "scripts": {
        "test": "jest",
        "start": "node server.js",
        "dev": "nodemon server.js"
    }
```
#### **Atualizando scripts**
#### Crie um auivo chamado `app.test.js`

#### **Importar superjest e app**
```javascript
    const request = require("supertest");
    const app = require("../app");
```
### `Funções JEST`
#### **describe()** agrupa um conjunto de testes individuais
#### **test()** ou **it()** (ambos fazem o mesmo, mas para ser mais intuitivo neste exemplo vou usar test()), que realiza um teste individual.

#### **Criando a primeira função**
```javascript
    describe("Test example", () => {
        // Código do teste aqui
    })
```
#### **Verificando primeira rota get**
```javascript
    describe("Test example", () => {
        test("GET /all", (done) => {
            // adicionar lógica aqui
        })
    // Código do teste aqui
    })
```
#### **Usando supertest**
```javascript
    describe("Test example", () => {
        test("GET /all", (done) => {
            request(app)
            .get("/all")
            .expect("Content-Type", /json/)
            .expect(200)
        });
    });
```
#### **Testando resposta**
```javascript
    describe("Test example", () => {
        test("GET /all", (done) => {
            request(app)
            .get("/all")
            .expect("Content-Type", /json/)
            .expect(200)
            .expect((res) => {
                res.body.data.length !== 0;
            });
        });
    });
```
#### **Finalizando teste individual**
```javascript
    describe("Test example", () => {
        test("GET /all", (done) => {
            request(app)
            .get("/all")
            .expect("Content-Type", /json/)
            .expect(200)
            .expect((res) => {
                res.body.data.length !== 0;
            });
        .end((err, res) => {
            if(err) return done(err);
            return done();
        })
        });
    });
```
