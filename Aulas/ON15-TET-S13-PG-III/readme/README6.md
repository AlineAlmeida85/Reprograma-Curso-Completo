## `Criando um Projeto Guiado - CRUD - Criando o DELETE` 
___


#### #### Rota ok e funcionando! Vamos agora fazer o `DELETE`.
```javascript
    const deleteNote = async (req, res) => {
    try {
    // acessar o documento a ser deletado
    const findNote = await NoteSchema.findById(req.params.id)
    // deletar o documento
    await findNote.delete()

    res.status(200).send({
        "message": "Nota deletada com sucesso!",
        findNote
    })
    } catch(err) {
        console.log(err);
    }
}

```
#### Vamos exportar ela:
```javascript
    module.exports = {
    getAll,
    createNote,
    updateNote,
    deleteNote
}
```
#### Configurar a rota:
```javascript
    router.delete("/delete/:id", controller.deleteNote)
```
