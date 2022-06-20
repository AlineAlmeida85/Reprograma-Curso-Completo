## ✔️ `If / else`
___
#### A condicional if é uma estrutura condicional que executa a afirmação, dentro do bloco, se determinada condição for verdadeira. Se for falsa, executa as afirmações dentro de else. (MDN) Podemos encadear vários ifs com else if
___
## Exemplos:

### if e else
```javascript
var horario = "01";

if(horario <= 12){
    console.log("dia");
} else{
console.log("tarde");
}
```
#### Explicação da lógica: temos uma `variável` de nome `horario` que recebe o valor `01`, Se o valor de horario for menor ou igual a 12 `if(horario <= 12)`, o console exibirá:
```javascript
dia
```
#### senão `else`, , o console exibirá:
```javascript
tarde
```
___
#### Podemos reduzir ao operador ternário:
```javascript
horario < 12 ? console.log("dia") : console.log("noite");
```
___
### If e else if

```javascript
var horario = "01";
var periodo = "";

if( horario <= 4){
    periodo = "madrugada";
}else if(horario <= 12) {
    periodo = "manhã";
}else if (horario <= 18){
    periodo = "tarde";
}else {
    periodo = "noite";
}
console.log(`São ${horario} da ${periodo}`);

São 01 da madrugada
```
#### Explicação lógica: temos uma `variável` chamada `horario` que recebe o valor `01`, e temos uma `variável` com o nome `periodo` que `não recebe valor`. Porque que ela não recebe valor? Porque o valor será de acordo com a hora informada!Vamos lá! Se horario for menor ou igual a 04 `if( horario <= 4)`, a variável `periodo` receberá o valor `madrugada`
#### E o resultado será: 
```javascript
São 01 da madrugada
```
