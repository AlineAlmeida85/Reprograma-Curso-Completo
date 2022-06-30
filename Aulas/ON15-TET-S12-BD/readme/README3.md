## `Resumo do App com MongoDB Completo da Aula` ✔️
___

#### Começamos assim:
```git
    touch server.js

    npm init -y

    touch .env
```

## Código `.env` :
```javascript
    PORT=8000
    MONGODB_URI=mongodb+srv://Aline:carlos01@cluster0.drwi8.mongodb.net/reprogramaMusic
```
___
#### Agora vamos instalar as `dependências`:
```git
    npm i express

    npm i cors

    npm i dotenv-safe

    npm i mongoose

    npm i -D nodemon
```
#### Feito isso vamos configurar o arquivo `server.js`. 
## Código `server.js` :
```javascript
    const app = require('./src/app')

    const PORT = process.env.PORT

    app.listen(PORT, () => console.log(`Tudo bem não funcionar, mas se rodar, vá na porta ${PORT}`))
```
#### Agora vamos rodar o servidor:
```git
npm start
```
#### Agora vamos no arquivo `mongooseConnect.js` criar essa conexão. 
## Código `moogoseConnect.js` :
```javascript
    const mongoose = require('mongoose')

    const MONGODB_URI = process.env.MONGODB_URI

    const connect = async () => {
        try {
            await mongoose.connect(MONGODB_URI, {
                useNewUrlParser: true,
                useUnifiedTopology: true
            })
            console.log('Banco Conectado com Sucesso!')
        } catch(error) {
            console.error(error)
        }
}

module.exports = { connect }
```
#### Terminamos o processo de configuração do banco de dados. Agora vamos para o arquivo `musicModel.js`.
## Código `musicModel.js` :
```javascript
    const mongoose = require("mongoose")

    const MusicSchema = mongoose.Schema({
        _id: mongoose.Types.ObjectId,
        artista: String,
        compositor: [String],
        titulo: String,
        categoria: [String],
        anoDeLancamento: Date,
        clipe: Boolean,
        imagens: [String],
        curtidas: Number
    }, { timestamps : true })

    const Model = mongoose.model("musica", MusicSchema)

module.exports = Model


```
#### Agora vamos para o arquivo `musicController.js` e vamos criar nossa primeira função.
## Código `musicController.js`:
```javascript
    const MusicModel = require("../models/musicModel")

    const createMusic = async (request, response) => {
        try {
            const newMusic = new MusicModel(request.body)
            const savedMusic = await newMusic.save()

            response.status(201).json(savedMusic)
        } catch (error) {
            response.status(500).json({ message: error.message })
        }
}

module.exports = {
    createMusic
}
```

#### Vamos agora para o arquivo `musicRoutes.js`.
## Código `musicRouter.js` :
```javascript
    const controller = require("../controller/musicController")

    const express = require("express")

    const router = express.Router()

    router.post("/music/create", controller.createMusic)

    module.exports = router
```
#### Agora vamos para o arquivo `app.js`. 
## Código `app.js` :
```javascript
    
    const express = require("express")
    require("dotenv").config()
    const cors = require("cors")
    const db = require("./database/mongooseConnect")
    const musicRoutes = require("./routes/musicRoutes")

    const app = express()

    app.use(express.json())
    app.use(cors())

    db.connect()

    app.use(musicRoutes)

    module.exports = app
```
#### Agora vamos no `MongoDb` ver o resultado!

## A Arquitetura:
```

    ReprogramaMusic  
    └─ api_com_mongo           
         ├─ src                       
         │  ├─ controllers 
         |  |         
         │  │  └─ nomeDaSuaController.js  
         │  ├─ database    
         |  |         
         │  │  └─ moogoseConnect.js 
         |  |   
         │  ├─ models                 
         │  │  └─ nomeDaSuaModel.js    
         |  |
         │  ├─ routes                 
         │  │  └─ nomeDaSuaRota.js  
         |  |  
         │  └─ app.js       
         |          
         ├─ package-lock.json         
         ├─ package.json  
         ├─ .gitignore            
         └─ server.js
```
