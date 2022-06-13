## ✔️ `Switch / case`
___
#### A condicional switch avalia uma expressão, combinando o valor da expressão para um cláusula case, e executa as instruções associadas ao case. (MDN) Passamos o break para sair da condicional quando um case é correspondido e sua instrução executada. Caso nenhum case seja correspondido podemos usar a cláusula default (opcional)
```javascript
let regiao = 'centro-oeste'

switch (regiao) {
    case 'nordeste':
        console.log('possui 9 estados');
        break;
    case 'norte':
        console.log('possui 7 estados');
        break;
    case 'centro-oeste':
        console.log('possui 3 estados e DF');
        break;
    case 'sudeste':
        console.log('possui 4 estados');
        break;
    case 'sul':
        console.log('possui 3 estados');
        break;
}
```
#### Explicação da lógica: temos uma variável chamada `let regiao` que no caso recebe o valor `= 'centro-oeste'`. Caso a variável regiao receba o valor `'nordeste'` o console exibirá ` console.log('possui 9 estados');`; Caso a variável regiao receba o valor `'norte'` o console exibirá ` console.log('possui 7 estados');`; Caso a variável regiao receba o valor `'centro-oeste'` o console exibirá ` console.log('possui 3 estados e DF');`;Caso a variável regiao receba o valor `'sudeste'` o console exibirá ` console.log('possui 4 estados');`e Caso a variável regiao receba o valor `'sul'` o console exibirá ` console.log('possui 3 estados');`.