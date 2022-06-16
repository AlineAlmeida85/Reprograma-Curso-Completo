## ✔️ `Nosso Primeiro Servidor Passo-a-Passo 3`


___
## `Criando uma rota de cadastro`
#### Vamos criar agora o método `POST`. Mão na massa!!
#### E já que o método é o Post, iniciamos com o `app.post`, configurar a rota `("products/cadastrar")` que terão uma request e uma response `(request, response)` seguido de uma arrow function... Até aqui nosso código esta assim:
```javascript
app.post("products/cadastrar", (request, response) => {

})
```
#### Vamos, aqui, usar o `body`, ele será usado no `Post`, no `Put` e no `Path`, vamos cadastrar dados e enviar para o arquivo `.json` no caso. Pra isso, a primeira coisa que temos que fazer é pegar a requisição. Criar uma variável chamada `bodyRequest` que será `igual` a `request.body.title`.
```javascript
let bodyRequest = request.body.title
```
#### Retornou um erro gigantesco!! Então temos que usar o `parser` porque ele vai pegar o valor quebrado e transforma num `json`. Então lá no começo do meu código, eu vou fazer um:
```javascript
app.use(express.json())
```
