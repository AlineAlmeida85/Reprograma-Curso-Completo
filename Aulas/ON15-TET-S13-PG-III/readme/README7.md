#### Hoje vamos criar um projeto guiado desde o inicio. Na pasta raiz do projeto vamos dao o comando:
```git
    npm install
```
___
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
2. Arquivo `server.js` 
```javascript
    const app = require('./src/app'); // requerindo o arquivo app.js pra ser usado neste arquivo
    const PORT = 3000; // definindo a porta de conexão

    app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`)); // criando a conexão do servidor
```
___

3. Arquivo `package.json` vamos na parte de `scripts`
```javascript
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
```

```git
    npm start
```
___
4. Arquivo `mongoConfig`
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
___
5. Arquivo `.env` 
```git
MONGODB_URI="mongodb+srv://Aline:<password>@cluster0.drwi8.mongodb.net/myFirstDatabase"
```
___
6. Arquivo `mongoConfig.js`
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
___
7. Arquivo `server.js`
```javascript
    const app = require('./src/app')
    const PORT = process.env.PORT

    app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`))
```
8. Arquivo  `.env`
```javascript
    MONGODB_URI=mongodb+srv://Aline:Carlos01@cluster0.drwi8.mongodb.net/NotePad
PORT=8088
```
___
9. Arquivo `.env.example`
```javascript
    MONGODB_URI
    PORT
```
___
10. Arquivo `app.js`
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
___
11. Montando nosso schema:
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
___
12. Criando o `GET` - arquivo `noteController.js`.
```javascript
    const NoteSchema = require("../moodels/noteSchema") // requerindo o schema pra este arquivo

    const getAll = async (req, res) => {
        try {
            const allNotes = await NoteSchema.find()
            res.status(200).send(allNotes)
        } catch (err) {
            console.log(err)
        }
    }; // criando uma variável que recebe uma função assíncrona e anônima que vai trazer o schema como resultado da busca.
```
#### Agora vamos exportar essa função:
```javascript
    module.exports = {
    getAll
}
```
#### Vamos então para o nosso arquivo `noteRoutes.js` para configurar a função na rota:
```javascript
    const express = require("express"); // requerindo o express para este arquivo
    const router = express.Router(); // requerindo a função router do express

    const controller = require("../controller/noteController") // requerindo a controller para este arquivo

    router.get("/all", controller.getAll); // criando a rota get

    module.exports = router;// exportando a função router
```
___
13. Criando o `POST`
```javascript
    const createNote = async (req, res) => {        
    try {
        const newNote = new NoteSchema({
            _id: new mongoose.Schema.Types.ObjectId,
            author: req.body.author,
            title: req.body.title,
            createdAt: new Date()
        })
        console.log("NOVA NOTA", newNote);

        const savedNote = await newNote.save();

        if(savedNote){
        res.status(201).send({
            "message": "Nota criada com Suceso!",
            savedNote
            })
        }

    } catch(err) {
        console.log(err);
    }
    
}
```
#### Agora no arquivo routes:
```javascript
    router.post("/create", controller.createNote)
```
14. Criando o `PUT` 

```javascript
const updateNote = async (req, res) => {
    try{
        // atualizar o documento a partir do id
        // receber esse is da requisição
        // encontrar o documento que possui aquele id

        const findNote = await NoteSchema.findById(req.params.id)

        if(!findNote) {
            res.status(404).send({
                "message": "Nota não encontrada!",
                "statusCode": 404
            })
        }
        // confiro as informações atualizadas        
        findNote.author = req.body.author || findNote.author
        
        findNote.title = req.body.title || findNote.author
        // salvo as atualizações

        console.log("Nota Atualizada", findNote)
        const savedNote = await findNote.save()
        // envio a resposta
        res.status(200).send({
            "message": "Nota Atualizada com Sucesso!",
            findNote
        })


    } catch(err) {
        console.log(err);
    }
}
```
#### Agora vamos exportar:
```javascript
    module.exports = {
    getAll,
    createNote,
    updateNote
}
```
#### E vamos configurar a rota:
```javascript
    router.put("/update/:id", controller.updateNote)
```
15. Criando o DELETE` 
___

```javascript
    const deleteNote = async (req, res) => {
    try {
    // acessar o documento a ser deletado
    const findNote = await NoteSchema.findById(req.params.id)
    // deletar o documento
    await findNote.delete()

    res.status(200).send({
        "message": "Nota deletada com sucesso!",
        findNote
    })
    } catch(err) {
        console.log(err);
    }
}

```
#### Vamos exportar ela:
```javascript
    module.exports = {
    getAll,
    createNote,
    updateNote,
    deleteNote
}
```
#### Configurar a rota:
```javascript
    router.delete("/delete/:id", controller.deleteNote)
```
#### Finalizado com sucesso!!!


