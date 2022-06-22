## ✔️ `Revisão`
___
#### Essa revisão vai te ajudar a relembrar conceitos e modelos para estabelecer o seu mapa mental de aprendizado! 😃

## `Node.js`
#### É um interpretador Javascript que não depende do navegador.

#### Ele é formado pelo V8, motor interpretador de Javascript criado pelo Google, e pela libuv, uma biblioteca que deu características de linguagem back-end para o node.

#### Node.js revolucionou a forma de programar em Javascript, pois a linguagem evoluiu de uma forma de dar vida aos elementos no navegador para uma linguagem capaz de rodar sistemas em computadores/servidores.

## `HTTP`
#### É o protocolo de transferência de hipertexto.

#### O principal protocolo de comunicação entre computadores utilzados na internet.

#### Ele cria as regras para enviar e receber informações na internet.

#### Ele é responsável pelo o que acontece por debaixo dos panos quando usamos a internet.

## `Verbos ou métodos`
#### É simples de entender:

#### `GET`: para consultas
#### `POST`: para criação de informações
#### `API`
#### Interface entre aplicativos e programação.

#### Se uma interface de um sistema é criado para o usuário final, a API é desenvolvida para que um sistema possa usar as funcionalidades de outro sistema.

#### Interface ideal para que um sistema se comunique com outro sistema.

## `REST e RESTful`
#### Rest é uma abstração(forma de usar as regras) do protocolo HTTP para simplificar a construção de um web service, ou seja quem cria uma API com as restrições e regras do modelo Rest está criando na verdade API Restful.

#### O grande objetivo desse modelo é fazer com que os recursos estejam disponíveis através de URLs.

#### Algumas das regras:
- Adotar convenção de URLs
- Basear em recursos
- Usar os verbos HTTP para indicar ações
- Ser stateless, ou seja, toda requisição é autossuficiente/independente
## `Arquitetura MVC`
```
        📂 API     
        ├─ 📂 src                       
        │  ├─ 📂 controllers            
        │  │  └─ produtoController.js          
        │  ├─ 📂 models                 
        │  │  └─ produtoModel.js      
        │  ├─ 📂 routes                 
        │  │  └─ produtoRouter.js            
        │  └─ app.js                 
        ├─ package-lock.json         
        ├─ package.json  
        ├─ .gitignore 
        ├─ README.md             
        └─ server.js
```
### `Server.js`
#### Aqui no server que você vai chamar o app para escutar a porta e disponibilizar toda a aplicação a partir do localhost

### `App.js`
#### Aqui no app que você vai usar a rota raiz

### 📂 Routes
#### Aqui nas rotas você vai usar os verbos para executar os controllers

### 📂 Controller
#### Aqui no controller você vai acessar os dados do seu model a partir das requisições e enviar respostas

### 📂 Model
#### Por enquanto estamos apenas guardando nosso JSON aqui, mas no futuro será o lugar onde você irá modelar os esquemas de dados para o banco. Não fique ansiosa! Acredite no processo, ele funciona!

