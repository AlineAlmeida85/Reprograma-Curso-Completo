## ✔️ `Nosso Primeiro Servidor Passo-a-Passo 5` 
___


#### Construindo nossa rota `PATCH`.
#### Chamamos o `app.patch` passando a minha rota`("/products/update/:id")` com o `(request, response)` seguido da callback `=> { }`. Pronto! A estrutura bpasica está criada.
```javascript
app.patch("products/update/:id", (request, response) => {

})
```
#### Agora vamos criar uma variável que vai pegar o id da request `const idRequest = request.params.id`.
```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    
})
```
#### Agora vamos criar outra variável chamada novoProduto que vai receber o produto que veio da request `const newTitle = request.body.title`.
```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title
    
})
```
#### Agora vamos encontrar o produto que tem esse id `const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)`.
```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title
    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)
})
```
#### Agora que encontrei o produto, ele será o novo titulo `produtoEncontrado = newTitle`.
```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title

    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)

    produtoEncontrado = newTitle
})
```
#### E pronto!! Nossa rota PATCH está pronta. Agora vamos fazer a response:
```javascript
response.status(200).json([{
    "Mensagem": "Título atualizado com sucesso!!",
    "produto-atualizado": produtoEncontrado,
    produtosJson
}])
```
#### Agora nosso código está pronto.
```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title

    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)

    produtoEncontrado = newTitle

    response.status(200).json([{
    "Mensagem": "Título atualizado com sucesso!!",
    "produto-atualizado": produtoEncontrado,
    produtosJson
}])
})
```
#### Concluído.