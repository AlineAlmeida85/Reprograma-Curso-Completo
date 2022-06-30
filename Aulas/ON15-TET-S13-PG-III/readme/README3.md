## `Criando um Projeto Guiado - CRUD - Criando o GET ` 
___


#### Vamos agora construir nossa primeira rota: o `GET`, chamado... `GetAll`.
- `GetAll` - leitura de todas as notas cadastradas no meu banco de dados
- Verbo Http: `GET`
- Definir uma rota: `/all`
#### Agora vamos analisar... ja definimos nosso `schema` e a configuração do banco, agora vamos para nossa analisar:
#### A `src/controller` - armazena a lógica e:
- required do schema, porque ele que conecta com a collection do banco de dados e é o esqueleto das minhas informações
- dentro de uma função anônima, recebo a requisição e a resposta
- envio as informações de todas as notas do meu banco de dados
- exportar essa função para ser acessada nas rotas

#### O `src/routes`:
- importar o express e definir o router
- required do arquivo de controller
- conectar a função criada com a rota criada
#### Sabendo disso vamos então para o nosso arquivo `noteController.js`.
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
#### Agora vamos para o `Postman` testar a rota criada `http://localhost:8080/notes/all` e o resultado será um objeto vazio mas, se olharmos no `MongoDB`... o nosso banco foi criado!

