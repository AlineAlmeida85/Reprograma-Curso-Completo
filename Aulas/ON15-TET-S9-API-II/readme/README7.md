## ✔️ `Arquitetura` 
___

#### Vamos começar a organizar tudo! Até hoje nós estávamos fazendo tudo dentro de um arquivo só, o `server.js`. O antes:
- Acessando o JSON
- Conectando como Express
- Criando as rotas
- Criando as lógicas
- Configurando a porta e iniciando o servidor

#### E tudo isso faz muito sentido se a gente tiver um projeto simples, mas... como a gente faz quando temos um projeto mais complexo? Depois:
- Acessando o JSON
- Conectando como Express
- GET/rota -> lógica
- GET/rota -> lógica
- POST/rota -> lógica
- POST/rota -> lógica
- GET/rota -> lógica
- PATCH/rota -> lógica
- DELETE/rota -> lógica
- GET/rota -> lógica
- Configurando a porta e iniciando o servidor

#### Não faz sentido esse monte de arquivos... 


## ✔️ `Arquitetura MVC` 
___
#### `MVC` é um padrão de arquitetura de software, separando sua aplicação em `3 camadas`. A camada de interação do usuário(`view`), a camada de manipulação dos dados(`model`) e a camada de controle(`controller`).
#### Já que estamos lidando com um projeto que tem `somente Back-End`, não lidaremos com as `views`, porém lidaremos com as rotas(`routes`).
#### O `MVC` nada mais é que uma forma de organizar o nosso código. 
- 1 - `Configurando a porta e iniciando o servidor` continua no arquivo `server.js`
- 2 - `Criação de rotas principais de requisição` ficarão num novo arquivo chamado `app.js`.
- 3 - `Pasta routes` ficarão as rotas que formos criando.
- 4 - As lógicas ficarão no arquivo `controller.js`.
- 5 - A pasta `model` ficará o `armazenamento` e a `gestão do banco de dados` que criamos.

___
#### Qual vai ser a organização que teremos agora? Essa: 
```
            📂 NOME-DO-SEU-PROJETO 
            |    
            ├─ package-lock.json         
            ├─ package.json  
            ├─ .gitignore 
            ├─ README.md             
            ├─ server.js
            ├─ 📂 src 
               |     
               ├─ app.js 
               |
               ├─ 📂 controller  
               |  |      
               │  └─ NOMEController.js  
               |      
               ├─ 📂 model 
               |  |            
               │  └─ NOMEModel.js  
               |    
               ├─ 📂 routes
               |  |             
               │  └─ NOMERouter.js  
               |                                   
            
```
| Arquivo ou pasta  | O que Armazena   |
|------------------ | ---------------- |
| `server.js`       | Configurar a porta e iniciar o servidor  |
| `app.js`          | Rotas principais de requisição           |
| `routes`          | Rotas e Verbos                           |
| `controller`      | Lógica                                   |
| `model`           | Armazenamento e gestão do banco de dados |

