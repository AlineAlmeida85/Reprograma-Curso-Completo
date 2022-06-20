## `CORS`


___
#### `CORS (Cross-Origin Resource Sharing) é uma especificação permite que um site acesse recursos de outro site mesmo estando em domínios diferentes.` 
#### Os navegadores fazem uso de uma funcionalidade de segurança chamada `Same-Origin Policy`: um recurso de um site só pode ser chamado por outro site se os 2 sites estiverem sob o mesmo domínio.
#### Isso porque o navegador considera recursos do mesmo domínio somente aqueles que usam o `mesmo protocolo` (http ou https), a `mesma porta` e o `mesmo endereço`.
#### Comando para instalar:
```javascript
npm install cors
```
#### Pensando assim, o front-end e o back-end deveriam estar no mesmo Servidor e na mesma camada, o que não acontece! Para resolver esse problema usamos o CORS.