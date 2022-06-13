## `Variáveis`
### Uma variável é um símbolo que referencia um espaço na memória do computador utilizado para armazenar dados que serão utilizados pelo programa em questão.
#### Para criar variáveis no JavaScript seguimos algumas regras importantes, a primeira e mais importante é que usamos uma das palavras reservadas var, let ou const para reservar o espaço na memória onde o dado será armazenado.
```javascript
var nome = "Lilit"
const sobrenome = "Bandeira"
let telefone = 11949801350
```
#### A segunda, baseada no exemplo das variáveis acima, é que para atribuir um valor a uma variável temos a seguinda estrutura:
```javascript
// palavra reservada -> var, const ou let
// identificador -> nomeDaVariável
// operador de atribuição -> =
// dado atribuido à variável -> String, number, boolean...
var curso = "reprograma" 
let numeroDaTurma = 15
const turmaEmAndamento = true
```
#### A terceira, também seguindo o exemplo das variáveis acima, o JavaScript é case sensitive, ou seja é sensível as diferenças entre letras maísculas e minúsculas, além de seguir o padrão camelCase, ou seja, para criar variáveis com nomes compostos, juntamos as palavras sempre iniciando a próxima com letra maiúscula, o que cria uma silhueta que remete a um Camelo, dizem shuahsuah
```javascript
//nomedaaluna não é a mesma coisa de nomeDaAluna
```
#### Outras regrinhas importantes:
#### As variáveis devem ter seus identificadores iniciando com letra (convencionalmente minúscula), underscore e cifrão e não podem iniciar com números;
#### No corpo do identificador ainda podem haver números e símbolos, mas não pode conter espaço;
#### Não é possível usar uma palavra reservada para nomear uma variável. Dica de boa prática:

#### **Utilize nomes descritivos para as variáveis, que ao ler, qualquer outra pessoa desenvolvedora que esteja lendo o código possa identificar o tipo de dado e seu objetivo no código, é mais indicado usar um identificador grande e descritivo do que pequeno e genérico**
```javascript
let cidadeOndeNasceu = "Rio de Janeiro"
let cidNasc = "Rio de Janeiro"
```
#### Quando usar `var`, `let` e `const`?

#### `var`: variáveis de `escopo global`, podem ser definidas, acessadas e atualizadas em qualquer parte do código;
#### `let`: variáveis de `escopo definido e bloqueado`, não podem ser acessadas fora do escopo onde foram definidas, porém podem ser atualizadas;
#### `const`: são constantes, ou seja `variáveis imutáveis`, não podem ser atualizadas, além disso, como o caso da let possui escopo definido e bloqueado, não podendo ser acessadas fora do escopo onde foram definidas;
#### É altamente recomendável utilizar var apenas em casos onde seja necessário, a boa prática é utilizar let e const para manter suas variáveis no escopo desejado e evitar que sofram mudanças indesejadas;