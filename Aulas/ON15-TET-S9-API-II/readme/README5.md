## ✔️ `PUT e PATCH`
___

#### `U: Update(atualizar)` - Atualizar os dados do registro.
#### É tudo a mesma coisa???
### Não!
#### O `PUT` substitui todo o objeto que voce deseja modificar, já o `PATCH` modifica somente uma propriedade dentro do seu objeto. Exemplo:


|  Dado inicial  |
| :------------: | 
| "Nome": "ana", |
| "idade": "18", | 
| "cor": "preta" |

### Resultado `PUT`, ele apaga tudo e mantém só o que eu atualizei:

|      PUT      |      DADO      |
| ------------- | -------------- | 
| "idade": "24" |  "idade": "24" |

### Resultado `PATCH`, mantém os dados e atualiza o que foi selecionado:

|     PATCH     |      DADO      |
| ------------- | -------------- | 
| "idade": "24" | "Nome": "ana", |
|               | "idade": "24", | 
|               | "cor": "preta" |

#### Mas então por que ainda usamos o `PUT`?
#### Muitas vezes ainda usamos o `PUT` pela performance que ele tem quando relacionado o banco de dados. Substituir um dado inteiro é mais rápido do que somente uma propriedade dele.

