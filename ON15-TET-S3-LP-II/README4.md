## ✔️ `for... of` 
### É um laço que percorre objetos iterativos, sendo o mais comum a array, chamando uma função para cada valor deste objeto;
```javascript
  for (variavel of iteravel) {
    declaração
  }
  ```
#### Exemplo:
```javascript
  // utilizaremos a mesma array números criada no exemplo do for.
  for (let numero of numeros) {
    const dobro = numero * 2;
    console.log(dobro);
  }
  ```

#### Explicação Lógica: Para variável numero de numeros `for (let numero of numeros) {`, a variável dobro recebe o valor de numero vezes 2 `const dobro = numero * 2;`, e o console exibirá o valor de dobro `console.log(dobro);`.
