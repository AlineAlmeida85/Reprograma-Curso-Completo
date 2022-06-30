### `GET ALL` - Leitura de todas as notas cadastradas no meu banco dados

### VERBO HTTP:
    - {GET}

### DEFINIR UMA ROTA: 
```
    /all
```
#### `src/controller` - armazena a lógica

- required do schema, porque ele que conecta com a collection do banco de dados e é o esqueleto das minhas informações
- dentro de uma função anônima, recebo a requisição e a resposta
- envio as informações de todas as notas do meu banco de dados
- exportar essa função para ser acessada nas rotas

#### `src/routes`
- importar o express e definir o router
- required do arquivo de controller
- conectar a função criada com a rota criada

#### `src/app` - descomentar linhas sobre rotas, testar no postman `\o/`.


___
### `CREATE NOTE` - Criar uma nota no banco de dados

### `VERBO HTTP`:
    - {POST}

### DEFINIR UMA ROTA: 
```
    /create
```
#### `editar`: arquivos controller e routes, testar no postman `\o/`
- ir no arquivo de rotas
- criar uma nova rota com o verbo POST
```
    Create => POST
    Read => GET
    Update => PUT, PATCH
    Delete => DELETE
```

### `UPDATE NOTE` - Atualizar uma nota no banco de dados

### `VERBO HTTP`:
- {PATCH} ou {PUT}?

### `DEFINIR UMA ROTA`: 
```
    /update/:id
```
#### `editar`: arquivos controller e routes, testar no postman `\o/`.


### `DELETE NOTE` - Deletear uma nota no banco de dados

### `VERBO HTTP`:
- {DELETE}

### `DEFINIR UMA ROTA`:
``` 
/
```
#### `editar`: arquivos controller e routes, testar no postman `\o/`.
