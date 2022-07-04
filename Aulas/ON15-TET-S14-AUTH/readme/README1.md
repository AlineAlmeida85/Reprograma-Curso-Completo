## `Por que Criptografar?` 
___



### Quando falamos em criptografia, o que vem á cabeça?
#### Criptografia é aprática de estudos e técnicas matemáticas para a comunicação segura na presença de terceiros. `É a transformação de uma informação em um formato que apenas as pessoas ou sistemas desejados consigam ler o conteúdo original.`
#### Após um dado ser criptografado, é possível descriptografar!
- Arquivos, banco de dados e trafegar dados em um canal não seguro.

___
## `Hash`


#### A função hash é um `algoritmo matemático para a criptografia`, na qual ocorre uma transformação do dado (como um arquivo, senha ou informações) em um conjunto alfanumérico com comprimento fixo de caracteres.

#### Após a conversão de um dado em hash, não é possível "`desconvertê-lo`".

</br></br>
<div align="center">
    <img src="https://static.imasters.com.br/wp-content/uploads/2017/02/net_cripto21.png" ><br>
</div>

- FEBRABAN (boleto bancário)
- MD5
- SHA (1/256/512)
- `BCRYPT`

___
## Por que não usar MD5?

- Muito rápido
- Vulnerável a colisões
- Famoso nas rainbow tables

___
## Tipos de Criptografia

#### `Simétrico` - Um dado é criptografado e descriptografado com a mesma chave.
- Exemplo: Sistemas internos
#### `Assimétrico` - Um dado é criptografado com uma chave pública e descriptografado com a chave privada. Chave pública e chave privada são diferentes.
- Exemplo: Aplicações bancárias, sistemas externos( Mercado Livre, GitHub)

___
## Token JWT

#### `Json Web Token` é um método utilizado para realizar autenticação entre duas partes por meio de um token. Esse token armazena objetos JSON com os dados que permitem a autenticação da requisição.

*Não é um hash e nem um tipo de criptografia!*

#### Por exemplo, uma requisição é realizada a um endpoint de login de uma API. No corpo da requisição são enviados `email` e `senha`. Após a autenticação ocorrer, o servidor cria um token JWT e o envia ao cliente, liberando seu acesso a demais endpoints.
___
## Agora vamos recapitular
- `CRIPTOGRAFIA` - Maneira de transformar caracteres de um dado para tornar a comunicação segura na presença de terceiros. Tecnicamente, pode ser simétrica ou assimétrica.
- `HASH` - Função matemática que permite a conversão direta de um dado em caracteres alfanuméricos com limite fixo.
- `TOKEN JWT` - É um método de autenticação entre duas partes, utilizando dados criptografados armazenados em um JSON

## `Autenticação x Autorização`
___

#### Quem é voce?
(logar, deslogar, verificar senhas)
#### Quem pode ver?
(permissões, controle de acessos)
___
## `Autenticação`

- `Formulários` -> não sou robô, seleção de imagens e afins
- `Redes Sociais` (`OAuth`) -> Login com redes sociais (google, facebook e afins)
- `Single Sign-on`(`Sitemas`) -> Empresas especializadas (biometria, autenticaçõ via código no Whatsapp, por ligação, sms)