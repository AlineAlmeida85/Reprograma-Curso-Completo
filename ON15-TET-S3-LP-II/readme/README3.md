## ✔️ `do... while`
___
#### O do...while também repete até que a condição especificada seja falsa. Porém sua intrução é sempre executado pelo menos uma vez, independente da condição, pois primeiro ele faz do e depois testa a condição no while.
```javascript
  do {
    código aqui;
  } while (condicao);
  ```

#### Exemplo:
```javascript
  let total = 0; 
  let contador = 0;

  do{
      total += contador * 100;
      contador++
      console.log(`contando...${contador}`)

  } while(contador < 10)
   ```