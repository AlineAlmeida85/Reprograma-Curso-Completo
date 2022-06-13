## ✔️ `while`
___
### Tem um funcionamento muito parecido com o do for, de executar sua intrução desde que a condição seja verdadeira, é sempre possível substituir o uso do for pelo do while, sendo o critério obter o código de melhor leitura, o while está mais atrelado à condição ser atendida enquanto o for é mais usado para iterar com contadores.
```javascript
  while (condicao) {
    código aqui;
  }
  ```

#### Exemplo:
```javascript
  let i = 1;
  while(i <=3) {
    console.log(`número ${i}`)
    i++
  }
```
#### Explicação lógica: a variável i recebe o valor 1 `let i = 1;`, enquanto o i for menor ou igual a 3 `while(i <=3) {`, exibirá no console o valor de i `console.log(`número ${i}`)` e depois acrescentará 1 `i++`.
#### Resultado: 
<p align="center">
  <img alt="foto" title="foto" src="./img/foto02.png"/>
</p>