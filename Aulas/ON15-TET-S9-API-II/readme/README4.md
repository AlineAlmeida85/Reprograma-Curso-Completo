## ✔️ `Passo a Passo da Construção do Servidor Resumido` 
___

## ✔️ `Nosso Primeiro Servidor Passo-a-Passo 4` 
___


#### Construindo nossa rota `DELETE`. 
```javascript
app.delete("/products/deletar/:id", (request, reponse) => {

})
```
#### Pronto! Montada nossa estrutura básica dp método `DELETE`. Agora vamos encontrar o item para deletar. 
```javascript
app.delete("/products/deletar/:id", (request, reponse) => {
    const idRequest = request.params.id
})
```
#### Então consegui pegar o que foi enviado no meu path params.
```javascript
app.delete("/products/deletar/:id", (request, reponse) => {
    const idRequest = request.params.id
    const produtoEncontrado = produtosjson.find(produto => produto.id == idRequest)
})
```
####  Agora vamos usar o método `splice`.
```javascript
    const indice = produtosjson.indexof(produtoEncontrado)
```
#### Agora vamos usar o splice. 
```javascript
produtosjson.splice(indice, 1)
```
#### E agora vamos fazer a response. 
```javascript
response.status(200).json([{
    "Mensagem": "Produto Deletado com Sucesso!!!",
    "produto-deletado": produtoEncontrado,
    produtosjson
}])
```
#### E nosso método DELETE está pronto!


___
#### Construindo nossa rota `PUT`. 
```javascript
app.put("products/atualizar/:id", (request, response) => {

})
```
#### Pronto...! A base ja está feita. 
```javascript
const idRequest = request.params.id
```

```javascript
const produtoAtualizado = request.body
```

```javascript
const produtoEncontrado = produtosjson.find(produto => produto.id == idRequest)
```

```javascript
const indice = produtosjson.indexOf(produtoEncontrado)
```

#### Nosso código está assim até agora:
```javascript
app.put("/products/atualizar/:id", (request, response) => {
    const idRequest = request.params.id
    const bodyRequest = request.body
    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)
    const indice = produtosJson.indexOf(produtoEncontrado)
    
    bodyRequest.id = idRequest

    console.log(produtosJson.splice(indice, 1, bodyRequest))

})
```

```javascript
produtosjson.splice(indice, 1, produtoAtualizado)
```
#### Agora vamos criar a `response`:
```javascript
response.status(200).json([{
    "Mensagem": "Produto Atualizado com Sucesso!!",
    "produto-atualizado": produtosjson
}])
```
#### Pronto! Nosso método PUT esta funcionando perfeitamente!" E o nosso código ficou assim:
```javascript
app.put("/products/atualizar/:id", (request, response) => {
    const idRequest = request.params.id
    const bodyRequest = request.body
    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)
    const indice = produtosJson.indexOf(produtoEncontrado)
    
    bodyRequest.id = idRequest

    produtosJson.splice(indice, 1, bodyRequest)

    response.status(200).json([{
        "Mensagem": "Produto Atualizado com Sucesso!!",
        "produto-atualizado": produtosJson
    }])

})
```

#### Construindo nossa rota `PATCH`.
___
#### A estrutura bpasica está criada.
```javascript
app.patch("products/update/:id", (request, response) => {

})
```

```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    
})
```

```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title
    
})
```

```javascript
app.patch("products/update/:id", (request, response) => {
    const idRequest = request.params.id
    const newTitle = request.body.title
    const produtoEncontrado = produtosJson.find(produto => produto.id == idRequest)
})
```

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