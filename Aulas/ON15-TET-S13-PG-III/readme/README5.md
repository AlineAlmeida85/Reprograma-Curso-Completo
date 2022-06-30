## `Criando um Projeto Guiado - CRUD - Criando o PUT` 
___


#### Agora vamos criar outra rota: o `PUT`, buscando por Id: 
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
