## ✔️ `Parâmetros`
___

### `Path params`
- são aqueles que são adicionados diretamente na URL.
- "/rota/:id"
- request.params.id
- bons, porem limitantes, por exemplo, se quisermos filtrar por uma string.

___
### `Query params`
- são aqueles que são adicionados a chave e o valor desejados.
- "/rota?id=1234".
- request.query.id
- a forma mais efetiva de fazer requests com strings ou diversos valores.

#### Tanto o body quando o query e o path são parâmetros enviados na requisição e podem ser acessados pelo servidor afim de definir a requisição e as ações.

### `request.params`
#### usado para pesquisa simples, enviado diretamente na rota.

### `request.query`
#### usado para pesquisa de uma ou multiplas strings.

### `request.body`
#### usado para enviar dados que serão cadastrados no banco, podem ser combinados com o query ou o path params.


