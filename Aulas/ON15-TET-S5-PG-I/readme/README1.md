## ✔️ `Laços`
___
### Laços são estruturas de repetição que são executadas até que uma condição seja verdadeira. Como usá-los?

#### Para interar um Array, para repetir um bloco ( trecho ) de código, para automatizar um bloco de código, etc.


### Sintáse	Descrição
#### `For` repete um bloco de código enquanto uma condição for verdadeira.
#### `While` Caso a condição seja verdadeira, ele executa o bloco de código.
#### `Do While`	Execulta uma vez, independente se a condição seja verdadeira ou não, enquanto
#### `For of` (Intera) Percorre um Array.

#### Exemplos:
#### `For`
```javascript
for(let i = 0; i < 10; i++){ 
    console.log(`estamos no numero ${i}`)
}
```

#### `While`
```javascript
let total = 0; 
let contador = 0;
while(contador < 10){
    total += contador * 100;
    contador++
    console.log(`contando...${contador}`)
}
```

#### `Do While`
```javascript
let total = 0; 
let contador = 0;
do{
    total += contador * 100;
    contador++
    console.log(`contando...${contador}`)
} while(contador < 10)
```

#### `For of`
```javascript
    let aldeias = ["Aldeia da Folha", "Aldeia da Areia", "Aldeia das Nuvens", "Aldeia do Som"]
    for(let aldeia of aldeias){ 
        console.log(`Mostre para min a aldeia: ${aldeia}`)
    }
```
