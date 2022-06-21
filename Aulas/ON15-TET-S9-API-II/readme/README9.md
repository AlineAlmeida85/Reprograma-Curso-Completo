## ✔️ `Passo a Passo da Construção de um Servidor utilizando a Arquitetura MVC` 
___
#### Agora vamos criar a rota `getById` que receberá uma função assíncrona e um arrow function e que receberá uma request e uma response:
```javascript
const getById = async(request, response) => {

}
```
#### Vamos conectar com o banco de dados:
```javascript
const getById = async(request, response) => {
    const filmesJson = await dbConnect()
}
```
#### Agora vamos montar a estruturra ja vista antes:
```javascript
const getById = async(request, response) => {
  const filmesJson = await dbConnect()
  let idRequest = request.params.id
  let filmeEncontrado = filmesJson.find(filme => filme.id == idRequest)

  response.status(200).send(filmeEncontrado)
}
```
#### E depois exportamos como o anterior:
```javascript
module.exports ={
  getAll,
  getById
}
```
#### Agora temos que fazer no `filmesRouter.js`:
```javascript
router.get("/catalogo/:id", controller.getById)
```
#### Criada mais uma rota `GET`.
___
#### `Criando o método POST`.
#### Vamos voltar para o nosso arquivo `filmesController.js` e fazer con a mesma estrutura do anterior.
```javascript
const createMovie = async(request, response) => {

}
```
#### Vou agora usar as mesmas estruturas vistas anteriormente e o nosso código ficará assim:
```javascript
const createMovie = async(request, response) => {
  let filmesJson = await dbConnect()
  let bodyRequest = request.body

    let novoFilme = {
        id: (filmesJson.length)+1, 
        title: bodyRequest.title, 
        description: bodyRequest.description 
    }
    filmesJson.push(novoFilme)
    
    response.status(201).send({
        "mensagem": "filmes cadastrado com sucesso",
        novoFilme
    })
}
```
#### Exportando a função...
```javascript
module.exports ={
  getAll,
  getById,
  createMovie
}
```
#### E agora no arquivo `filmesRouter.js`:
```javascript
router.post("/criar", controller.createMovie)
```
#### Mas ainda faltou algo...
```javascript
app.use(express.json())
```
#### E para ser aplicado para todos, essa linha de código ficara no arquivo `app.js`.
