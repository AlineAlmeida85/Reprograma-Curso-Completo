## ✔️ `GET`
___

#### Dentro do CRUD o método GET é representado pela letra R R: Read (ler) - exibir as informações de um registro.
#### O Client manda um request solicitando realizar um GET e o Server deve estar preparado para receber esse GET e responde-lo com um response.
## `Criando o GET`
#### Vamos configurar a primeira rota. Existe uma função pra construir o `GET`. Mas antes disso vamos nos certificar que estamos com os arquivos que devemos ter até aqui.
<p align="center">
  <img alt="foto" title="foto" src="../img/foto12.png"/>
</p>

#### Como na foto acima devem ter estes arquivos no seu projeto.
#### Agora sim vamos partir para a primeira rota.
#### O `app.get` pois dentro do `Express` ja exite essa função `get` pronta e sempre que formos criar um `GET`, `POST`, `PUT`, `PATCH` ou `DELETE`, no primeiro parâmetro da função será a minha rota vazia só com a barra `("/")`, no segundo parâmetro será uma função `()` que vai receber o request e o response `(request, response)`, seguido de uma arrow function ` => ` e dentro dela será o que vai acontecer.
```javascript
app.get("/", (request, response) => {

})
```
#### Essa é a estrutura básica de uma requisição `get`. Então a `função get` espera que eu mande uma `rota`, e ela me retorna uma `outra função` (`callback`), e sempre vai me enviar uma `request` e uma `response`, porque são o que eu `preciso` pra fazer um `get`.
#### Aqui será onde vão acontecer as requisições(`request`), e se tem requisição eu vou enviar uma resposta, e nós como `Back-Ends` vamos configurar uma resposta(`response`) e pra fazer isso vamos fazer uma `response`, vou enviar um `.status`, colocando o número dele `(200)` pois é uma resposta positiva que queremos e vou mandar um `.json` falando `(["Salve, mundão"])`.
```javascript
app.get("/", (request, response) => {
  response.status(200).json(["Salve, mundão"])
})
```
#### Pronto! Criada a primeira rota. Agora vamos testar essa rota. Sempre que quiser `parar` o servidor, tecle `Ctrl C`.
