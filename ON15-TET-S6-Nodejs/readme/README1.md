## ✔️ `Modelo Server/Client`  


|                |  Servidor   | Cliente    |                |
| -------------- | ------------|------------|----------------|
| Usuários       | Client      | Server     | Banco de Dados |
|  ⇆             |  ⇆         |  ⇆         |    ⇆          |

#### O servidor conecta o cliente com o banco de dados
___
|   Servidor     |   Cliente   |            |
| -------------- | ------------|------------|
|                | DNS         |            |
| Usuários       | Client      | Server     |
| ➜             | ➜          | ➜         |

___

## ✔️ `Client`

### ***Client*** é a interface que os usuário interagem, é essa camada que é responsável de `solicitar` serviços e informações de um ou mais servidores.

#### Alguma tarefas a serem realizadas pelo cliente:

* manipulação de tela
* interpretação de menus ou comandos
* entrada e validação dos dados
* recuperação de erros
* Manipulação de janelas
* Gerenciamento de som e vídeo (em aplicações multimìdia)

## ✔️ `Server`

### O ***Servidor*** é o responsável pelo processo, organização e geenciamento das informações.
### É ele que `responde as solicitações` feitas pelo Client. Ele é um processo reativo, disparado pela chegada de pedidos de seus clientes.

#### O processo do servidor geralmente inclui:
* Acessar
* Organizar os dados compartilhados
* Fazer a comunicação com o Banco de Dados
* Atualizar dados previamente armazenados
* Gerenciamento dos recursos compartilhados

## ✔️ `O que acontece quando acessamos um site?`

        1. A URI é processada
        2. É feita uma requisição
        3. É dada uma Resposta
        4. A página é renderizada e aparece na tela
___
### 1. A URI é processada
#### Todo site tem um `domínio`, normalmente é por ele que acessamos e conhecemos o Site. Porém, no server esse site não está registrado pelo nome de domínio, e sim pelo `endereço de IP`.
#### Internet Protocol Address é o endereço exato onde o site está dentro do servidor.
#### Então, antes de uma requisição ser feita, o domínio deve virar o IP, e para isso, usamos o `DNS`, o Domain Name System(Sistema de nome de Domínio) que é como um grande dicionário de domínio para IP que já vem "de fábrica" no browser.
#### Para entendermos uma **URI** precisamos entender a **URL** e a **URN**
◼️ URL - Uniform Resourse Locator (localizador de recurso uniforme). Ela representa o local/host que estão localizados os recursos.

### URL ↓
#### `www.reprograma.com.br` - endereço do servidor, ou seja, a URL é o endereço de IP.

◼️ URN - Uniform Resource Name (nome de recurso universal). Ela representa um recurso específico na web que está sendo acessada.

### URN ↓
#### `/equipe.html`
#### `/alunas.html`
#### `/parcerias.html`

### URI ↓
◼️ URI - Uniform Resource Identifier (identificador de recursos universal). É o identificador contendo que une o protocolo HTTP + o localizador do recurso(URL) + nome do recurso.
#### Pode ser uma página HTML, imagem, vídeo ou qualquer outro arquivo web tem um endereço dentro da internet, esse endereço é a `URI`.

|   Protocolo    |   URL                 | URN              |
| -------------- | ----------------------|------------------|
| https://       | www.reprograma.com.br | /equipe.html     |
| protocolo      | endereço do servidor  | recurso          |
___
### 2. O Request é enviado
#### Agora com o endereço certo, o Client faz uma requisição, ou Request, cheio de informações desejadas.
#### Pra que isso aconteça, tanto o Server quanto o client devem "falar a mesma lingua".
#### Na maioria dos casos, essa comunicação entre Server e Client é feita a partir do `Protocolo HTTP`.
#### O protocolo de transferência de Hipertexto, o HTTP, é um protocolo usado dentro do modelo Client/Server é baseado em pedidos(requests) e respostas (responses).
#### O protocolo HTTP define um conjunto de métodos de requisição responsáveis por indicar a ação a ser executada.
#### Eles são chamados de `Verbos HTTP ou Métodos HTTP`.
#### Os verbos HTTP mais utilizados são:
* GET
* POST
* PUT
* PATCH
* DELETE
#### Cada um deles corresponde a uma ação real no banco de dados.

<div align="center">
        <table border=1>          
        <tr>
                <th>Verbo HTTP</th>
                <th>Ação</th>                
        </tr>
        <tr>
                <td align="center">GET</td>
                <td>Ler</td>
        </tr>
        <tr>
                <td align="center">POST</td>
                <td>Criar</td>
        </tr>
        <tr>
                <td align="center">PUT</td>
                <td>Substituir</td>
        </tr>
        <tr>
                <td align="center">PATCH</td>
                <td>Modificar</td>
        </tr>
         <tr>
                <td align="center">DELETE</td>
                <td>Excluir</td>
        </tr>
        </table>
</div>

### `CRUD` é o acrônimo em inglês de `C`reate, `R`ead, `U`pdate e `D`elete.
___
### 3. O Server responde
#### Quando o client faz um `Request` o Server envia um `Response`.
#### E na resposta tem, além do resultado do que foi pedido, um código de status numérico padronizado.

<div align="center">
        <table border=1>          
        <tr>
                <th>Código</th>
                <th>Tipo de Resposta</th>                
        </tr>
        <tr>
                <td align="center">100 - 199</td>
                <td>Informação</td>
        </tr>
        <tr>
                <td align="center">200 - 299</td>
                <td>Sucesso</td>
        </tr>
        <tr>
                <td align="center">300 - 399</td>
                <td>Redirecionamento</td>
        </tr>
        <tr>
                <td align="center">400 - 499</td>
                <td>Erro do Cliente</td>
        </tr>
         <tr>
                <td align="center">500 - 599</td>
                <td>Erro de Servidor</td>
        </tr>
        </table>
</div>

___
### 4. O site aparece na tela
#### Finalmente!!!


     