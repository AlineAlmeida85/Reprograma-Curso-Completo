## A arquitetura do Projeto
```
            ├─ ON15-TET-S14-AUTH
            ├─ node_modules           
            ├─ src                       
            │   ├─ config 
            |   |    └─ database.js       
            │   │  
            |   ├─ controllers   
            │   |    ├─ authController.js 
            |   |    └─ userController.js      
            │   │   
            |   ├─ models   
            │   |    └─ userSchema.js                
            │   │      
            |   ├─ routes
            │   |    └─ userRoutes.js                    
            │   │     
            |   |  
            │   └─ app.js       
            |          
            ├─ .env
            ├─ .env.example             
            ├─ .gitignore  
            ├─ package-lock.json
            ├─ package.json 
            ├─ README.md 
            ├─ server.js             
            └─ ToDO
```
## ➝ O Código Completo da Aula
___
## 📁 config ➝ 📋 `database.js`
```javascript
const mongoose = require('mongoose')

const connect = async () => {
    try {
        await mongoose.connect(process.env.MONGODB_URI, {
            useNewUrlParser: true,
            useUnifiedTopology: true
        })
        console.log("Banco conectado")
    } catch (error) {
        console.error("Erro: ", error.message)
    }
}

module.exports = {
    connect
}
```
___

## 📁 controllers ➝ 📋 `authController.js` 
```javascript
const UserSchema = require('../models/userSchema');
const bcrypt = require("bcrypt");
const jwt = require("jsonwebtoken");

const SECRET = process.env.SECRET;

const login = (req, res) => {
    try {
        UserSchema.findOne({ email: req.body.email }, (error, user) => {
            console.log("USUÁRIO:", user)
            if(!user) {
                return res.status(401).send({
                    "message": "User não encontrado",
                    email: `${req.body.email}`
                })
            }
            const validPassword = bcrypt.compareSync(req.body.password, user.password);
            console.log("A SENHA É VÁLIDA?", validPassword)

            if(!validPassword) {
                return res.status(401).send({
                    "message": "Login não autorizado"
                })
              }
              const token = jwt.sign({ name: user.name}, SECRET)
              console.log("Token criado", token);

              res.status(200).send({
                "message": "Login autorizado!",
                token
              });
        })
    } catch(e) {
        console.error(e)
    }
};

module.exports = {
    login
};
```
___

## 📁 controllers ➝ 📋 `userController.js`
```javascript
const UserSchema = require("../models/userSchema");
const bcrypt = require("bcrypt");
const jwt = require("jsonwebtoken");

const SECRET = process.env.SECRET;

const getAll = async (req, res) => {
  const authHeader = req.get('authorization');
  
  const token = authHeader.split(' ')[1];
  
  if (!token) {
    return res.status(401).send("Erro no header")
  }

  jwt.verify(token, SECRET, function(err) {
    if (err) {
      return res.status(403).send('Não autorizado');
  }
});

  UserSchema.find(function (err, users) {
    if(err) {
      res.status(500).send({ message: err.message })
    }
      res.status(200).send(users)
  }) 
};


const createUser = async (req, res) => {
  const hashDePassword = bcrypt.hashSync(req.body.password, 10)
  req.body.password = hashDePassword
  try{
    const newUser = new UserSchema(req.body);

    const savedUser = await newUser.save();
    
    res.status(201).send({
      "message": "Usuário criado com Sucesso!",
      savedUser
    })
  } catch(err) {
    console.error(err);
  };
}


module.exports = {
  getAll,
  createUser
};

```
___

## 📁 models ➝ 📋 `userSchema.js`
```javascript
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
    id: mongoose.Schema.Types.ObjectId,
    name: {
        type: String,
        required: true
    },
    email: {
        type: String,
        required: true
    },
    password: {
        type: String,
        required: false
    },
    createdAt: {
        type: Date,
        default: new Date()
    }
});

module.exports = mongoose.model('user', userSchema);
```
___

## 📁 routes ➝ 📋 `userRoutes.js`
```javascript
const express = require("express");
const router = express.Router();

const controller = require("../controllers/userController");
const authController = require("../controllers/authController");


router.get("/all", controller.getAll);

router.post("/create", controller.createUser);

router.post('/login', authController.login);

module.exports = router;

```
___

## ➝ 📋 `app.js`
```javascript
const express = require('express');
const app = express();
const cors = require('cors');

require('dotenv-safe').config();

const db = require('./config/database');
const userRoutes = require('./routes/userRoutes');

db.connect() ;

app.use(cors());
app.use(express.json());
app.use("/users", userRoutes);

module.exports = app;
```
___

## ➝ 📋 `.env`
```javascript
PORT=8000
MONGODB_URI=mongodb+srv://Aline:Carlos01@cluster0.drwi8.mongodb.net/users
SECRET=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCn/dUCfUHLoBRIsXhDArKYPXPLrjrEijcoIKoP+M3mzLYefBwxPN8EGXt821P2S+JQMzav8l6ZPAtTz8NluYEji/VsR3XfentcPZxQFgLf+U/myhIFU0natPq4SN37hFrmlHwbwf8w/C5Xzw9jfMNu+Ui76UAsDZFnql5bboYYGwIDAQAB

```
___

## ➝ 📋 `.env.example`
```javascript
PORT
MONGODB_URI
SECRET
```
___

## ➝ 📋 `server.js`
```javascript
const app = require('./src/app');
const PORT = process.env.PORT;

app.listen(PORT, () => console.log(`Servidor rodando na porta ${PORT}`));
```
___