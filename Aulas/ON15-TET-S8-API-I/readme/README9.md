## ✔️ `Passo a Passo da Construção da Aula sem Detalhes`
___

___
## `Iniciando o servidor`

```git
code .
```
#### Agora vamos criar nosso primeiro arquivo.
```git
touch server.js
```
#### Perceba que digitei o comando acima e depois digitei 
```git
ls
```
___
## `Iniciando o npm`
#### para listar os itens que tem na pasta e apareceu o arquivo que acabei de criar com o nome `server.js`. Agora digite:
```git
npm init -y
```
#### Ele vai criar tudo de uma vez, podendo depois irmos até o arquivo `package.json` e editar as informações posteriormente.

___
## `Dependências - Instalando o Express`
#### Continuando no nosso terminal, digite:
```git
npm install express
```
#### ou
```git
npm i express
```
#### Vá no `VSCode` e perceba que foram criados mais dois arquivos: o `package-lock.json` e a pasta `node_modules`.

___
## `.gitignore`
#### Agora digite:
```git
touch .gitignore
```
#### Para criar o arquivo `.gitignore`. ele vai ignorar tudo o que for incluso lá. Veja como incluir a pasta `node_modules` no .gitignore.

___
## `Chamando o Express no arquivo`
#### Na sequência, vá no arquivo `server.js` para chamarmos o `Express`.
#### Digite:
```javascript
const express = require("express")
```
___
## `Executando o Express no arquivo`
#### Agora precisamos executar o `Express`, por dentro, ele é uma grande função. Para executar ele faremos:
```javascript
const app = express()
```

___
## `Criando a Porta`
#### Agora vamos criar a porta.
```javascript
app.listen(8080, () => {
  console.log("Meu servidor está rodando na porta 8080 graças a Deus!")
})
```

___
## `Testando o Servidor`
#### Agora no seu terminal digite:
```git
npm start
```

___
## `Criando o GET`
#### Vamos configurar a primeira rota. 
```javascript
app.get("/", (request, response) => {

})
```

#### vamos configurar uma resposta(`response`)
```javascript
app.get("/", (request, response) => {
  response.status(200).json(["Salve, mundão"])
})
```
#### Pronto! Criada a primeira rota. Agora vamos testar essa rota. Sempre que quiser `parar` o servidor, tecle `Ctrl C`.

___
## `Testando a rota`
#### Inicie o servidor novamente digitando:
```git
npm start
```
#### Agora vamos abrir o `Postman`, ao lado digite:
```
localhost:8080/
```

___
## `Dependências - Instalando o Nodemon`

```git
npm install nodemon
```
#### ou
```git
npm i nodemon
```

#### Agora vamos configurar: no mesmo arquivo (package.json) um pouco pra cima, no `start`, onde está escrito `node server.js` vamos alterar... ja que é aqui que configuramos a fomra de `startar` nosso projeto. Vamos tirar o `node server.js` e escrever `nodemon server.js`.

```git
npm start
```

___
## `Criando uma rota real`

```git
mkdir data
```
#### Para criar a pasta e o comando:
```git
touch produtos.json
```
#### Rota:
```javascript
app.get("/products", (request, response) => {
  response.status(200)
})
```

```javascript
const produtosjson = require("./data/produtos.json")
```

#### O código ficará assim:
```javascript
app.get("/products", (request, response) => {
    response.status(200).send(produtosjson)
})
```

#### Agora vamos testar no `Postman`.

___
## `Criando uma rota buscando pelo ID`

```javascript
app.get("/products/buscar/:id", (request, response) => {

})
```
#### Agora eu quero fazer uma pesquisa e essa pesquisa tem que ser pelo ID.
```javascript
let idRequest = request.params.id
```
#### Agora iremos que percorrer o arquivo json que esta com as informações.
```javascript
let produtoEncontrado = produtosjson.find(produto => produto.id == idRequest)
```

#### Vamos então fazer o response que será o mesmo ja visto antes:
```javascript
response.status(200).send(produtoEncontrado)
```
## ✔️ `Nosso Primeiro Servidor Passo-a-Passo 3`


___
## `Criando uma rota de cadastro, POST`
#### Vamos criar agora o método `POST`.
```javascript
app.post("products/cadastrar", (request, response) => {

})
```
#### Vamos, aqui, usar o `body`, ele será usado no `Post`, no `Put` e no `Path`.
```javascript
let bodyRequest = request.body.title
```

```javascript
app.use(express.json())
```
#### Até aqui nosso código está assim:
```javascript
app.post("/products/cadastrar", (request, response) => {
    let bodyRequest = request.body    
    console.log(request.body)
})
```
#### Vamos fazer o seguinte: criar uma variável que vai se chamar `novoProduto`. Essa variável  que vai receber o novo produto:
```javascript
let novoProduto = {
        id: bodyRequest.id,
        title: bodyRequest.title,
        price: bodyRequest.price,
        description: bodyRequest.description,
        image: bodyRequest.image,
        category: bodyRequest.category
    }
```
#### Agora que tenho um novo objeto... :
```javascript
produtosjson.push(novoProduto)
```
#### Agora vamos fazer a `response`.
```javascript
response.status(201).send({
        "Mensagem": "Novo Produto cadastrado com sucesso!", 
        novoProduto
    })
```


#### O código do método `POST` completo do exemplo é este:
```javascript
app.post("/products/cadastrar", (request, response) => {
    let bodyRequest = request.body

    let novoProduto = {
        id: bodyRequest.id,
        title: bodyRequest.title,
        price: bodyRequest.price,
        description: bodyRequest.description,
        image: bodyRequest.image,
        category: bodyRequest.category
    }
    produtosjson.push(novoProduto)

    response.status(201).send({
        "Mensagem": "Novo Produto cadastrado com sucesso!", 
        novoProduto
    })
})
```

___
## `Dependências - Instalando o CORS`
#### Instalar o `CORS`:
```git
npm install cors
```
#### ou:
```git
npm i cors
```
#### Após isso, vá no seu arquivo `server.js`, onde tem as requisições e chame o CORS:
```javascript
const cors = require("cors")
```
#### Agora vamos usar:
```javascript
app.use(cors())
```

