## `Criando um Projeto Guiado - CRUD - Criando o POST` 
___


#### Agora... vamos criar um `POST`.
```javascript
    const createNote = async (req, res) => {        
    try {
        const newNote = new NoteSchema({
            _id: new mongoose.Schema.Types.ObjectId,
            author: req.body.author,
            title: req.body.title,
            createdAt: new Date()
        })
        console.log("NOVA NOTA", newNote);

        const savedNote = await newNote.save();

        if(savedNote){
        res.status(201).send({
            "message": "Nota criada com Suceso!",
            savedNote
            })
        }

    } catch(err) {
        console.log(err);
    }
    
}
```
#### Agora no arquivo routes:
```javascript
    router.post("/create", controller.createNote)
```
