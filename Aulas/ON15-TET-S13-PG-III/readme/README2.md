## `Criando um Projeto Guiado - CRUD - Comandos Básicos` 
___


### Tópicos das dúvidas:
- Conectar o banco no `.env`
- `SQL` e `NoSQL`
- Funções do `Mongoose` <> `JavaScript`
- Lógica das Pirmeiras Semanas no Projeto
    - `If` / `else`
- Tratamento de `Erros`
- `Assincronicidade`
- Conectar `duas models`
___
#### Hoje vamos criar um projeto guiado desde o inicio. Na pasta raiz do projeto vamos dao o comando:
```git
    npm install
```
#### Porque o projeto ja tem as dependências descritas, então com esse comando a node_modules vai aparecer. O nosso projeto é criarmos um mini bloco de notas. Então até aqui ja teremos algumas configurações do nosso projeto criadas, vamos ver:
1. Arquivo `app.js`
```javascript
    const express = require('express'); // requerindo o express

    const app = express(); // chamamos o express jogando ele numa variável

    const cors = require('cors'); // requerindo o cors
    app.use(cors()); // usando o cors

    require('dotenv-safe').config(); // requerindo o dotenv

    const db = require('./database/mongoConfig'); // requerindo o arquivo de configuração do banco de dados
    db.connect(); // chamando o banco de dados

    const noteRoutes = require('./routes/noteRoutes'); // requerindo o arquivo de rotas

    app.use(express.json()); // usando o express pra conseguir ler as informações que vem do body
    app.use("/notes", noteRoutes); // definindo a rota principal

    module.exports = app; // exportando o app para ser usado em outros arquivos
```
___
#### E...
2. Arquivo `server.js` 
```javascript
    const app = require('./src/app'); // requerindo o arquivo app.js pra ser usado neste arquivo
    const PORT = 3000; // definindo a porta de conexão

    app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`)); // criando a conexão do servidor
```
#### Essas são configurações que ja criamos nas aulas anteriores, mas os outros arquivos ainda não tem nada. Vamos definir como iniciar nosso projeto. Na pasta `package.json` vamos na parte de `scripts`:
```javascript
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
```
#### Vamos então deixar assim:
```javascript
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
```
#### Essa é a forma mais correta de manter o `script`. O `dev` utilizamos quando estamos desenvolvendo o projeto, que é o nosso caso, o com o `nodemon` o servidor vai atualizar automaticamente a cada atualização do projeto, já com o `start` teremos que a toda atualização interromper o servidor teclando o <kbd>CTRL + C</kbd> e iniciá-lo novamente usando o comando:
```git
    npm start
```
#### Então para darmos proceguimento ao nosso projeto, vamos usar o comando:
```javascript
    npm run dev
```
#### Mas vai dar um erro pois não configuramos o nosso banco de dados.
```git
    C:\Users\Adm\Documents\Reprograma\ON15-TET-S13-PG-III\src\app.js:10
db.connect();
   ^

TypeError: db.connect is not a function
    at Object.<anonymous> (C:\Users\Adm\Documents\Reprograma\ON15-TET-S13-PG-III\src\app.js:10:4)
    at Module._compile (node:internal/modules/cjs/loader:1105:14)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1159:10)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at Module.require (node:internal/modules/cjs/loader:1005:19)
    at require (node:internal/modules/cjs/helpers:102:18)
    at Object.<anonymous> (C:\Users\Adm\Documents\Reprograma\ON15-TET-S13-PG-III\server.js:1:13)
    at Module._compile (node:internal/modules/cjs/loader:1105:14)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1159:10)
[nodemon] app crashed - waiting for file changes before starting...
```
#### Se voce for tentar traduzir esse erro... esta dizendo exatamente o que eu falei antes... erro no `db.connect` pois o arquivo `mongoConfig`está vazio. Vamos então configurar ele agora.
```javascript
const mongoose = require("mongoose"); // requerendo o mongoose

const MONGODB_URI = process.env.MONGODB_URI; // definindo a URI de conexão com o banco de dados

const connect = async () => {
    try { // tenta criar a conexão executando esse código abaixo
        await mongoose.connect(MONGODB_URI, {
            useNewUrlParser: true,
            useUnifieldTopology: true
        }) // se conectar, mostre a mensagem
        console.log("Banco de Dados Conectado com Muitoo Sucessoo!")
    } catch (error) { // se der erro o código, pegue o erro e me mostre.
        console.log("Erro: ", error.message)
    }
        
} // aqui estamos criando uma variável que recebe uma função anônima e assíncrona, ou seja, é preciso esperar(await) a conexão com o banco acontecer pra aparecer a mensagem no console.

    module.exports = {  
        connect
    } // agora estamos exportando essa função de conexão pra ser usada em outro arquivo
```
#### Se não tem o `await`, ia aparecer a mensagem no console independente da conexão acontecer ou não.
___
#### Agora vamos falar sobre o `.env`. Vamos colocar a configuração dele: 
```git
MONGODB_URI="mongodb+srv://Aline:<password>@cluster0.drwi8.mongodb.net/myFirstDatabase"
```
#### Dei um nome qualquer para o banco de dados `FirstDataBase` pois ainda vamos criar um. Agora vamos ver como estão nossos arquivos:
### `mongoConfig.js`
```javascript
    const mongoose = require('mongoose')

    const MONGODB_URI = process.env.MONGODB_URI

    const connect = async () => {
    try {
        await mongoose.connect(MONGODB_URI, {
            useNewUrlParser: true,
            useUnifiedTopology: true
        })
        console.log("Banco de Dados Conectado com Muitoo Sucessoo!")
    } catch (error) {
        console.log("Erro: ", error.message)
    }
    
}

module.exports = {
    connect
}
```
### `server.js`
```javascript
    const app = require('./src/app')
    const PORT = process.env.PORT

    app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`))
```
### `.env`
```javascript
    MONGODB_URI=mongodb+srv://Aline:Carlos01@cluster0.drwi8.mongodb.net/NotePad
PORT=8088
```
### `.env.example`
```javascript
    MONGODB_URI
    PORT
```
### `app.js`
```javascript
    const express = require('express');
    const app = express();

    const cors = require('cors');
    app.use(cors());

    require('dotenv-safe').config();

    const db = require('./database/mongoConfig');
    db.connect();

    const noteRoutes = require('./routes/noteRoutes');

    app.use(express.json());
    app.use("/notes", noteRoutes);

    module.exports = app;
```
#### Agora que ja conectamos o nosse servidor e o nosso banco de dados... vamos codar! Montando nosso schema:
```javascript
    const mongoose = require("mongoose") // requerindo o mongoose

    const noteSchema = new mongoose.Schema({ // construindo o novo schema num objeto passando as caractrísticas desse objeto:
        id: mongoose.Schema.Types.ObjectId, // um tipo de id do mongo(ele vai criar pra nós)
        author:{
            type: String,
            required: true
        }, // autor como item obrigatório
        title: {
            type: String,
            required: true
        }, // titulo como item obrigatório
        createdAt: {
            type: Date,
            default: new Date()
        } // data de criação, o new date vai criar a data automaticamente
    });

module.exports = mongoose.model("note", noteSchema) // exportando o meu schema para usar em outros arquivos
```
