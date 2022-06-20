## ✔️ Callbacks
___
### É uma função passada como argumento para outra função, que será invocada dentro da função externa para completar uma determinada rotina/ação, podendo ser síncrona ou assíncrona;
### É o padrão assíncrono mais comum no JavaScript, sendo a base para lidar com execuções assíncronas na linguagem;
### Na programação assíncrona, callbacks são funções a serem executadas após um evento (como a resolução de uma requisição), permitindo operar livremente a partir do retorno de outras funções;
#### Exemplo:
```javascript
funtion elogiar(nome) {
    console.log(nome +", voce é linda!")
}
```
```javascript
funtion lerEntrada(callback) {
    let nome = "Liniker"
    return callback(nome)
}
```
