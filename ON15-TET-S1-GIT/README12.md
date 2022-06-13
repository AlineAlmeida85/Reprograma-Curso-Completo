## **Pull Request**, **Feature Branch** e **Resolvendo Conflitos**

#### `Pull Request` (ou PR): Utilizado para solicitar o merge de uma branch em outra branch no nosso repositório remoto.
#### Supondo que há mais de uma pessoa trabalhando no mesmo projeto, as duas alteraram esse projeto(cada uma na sua `branch`), sendo assim precisamos subir essas alterações no `GitHub`, porém vai gerar um conflito entre essas alterações.Vamos ao passo a passo de como resolver.
```git
git add .
```
```git
git commit -m "sua mensagem"
```
```git
git checkout branch
```
### O git irá listar conflitos, se digitarmos:
```git
git log
```
#### Poderemos ver os logs tanto de uma pessoa quanto da outra.
```git
git rebase main
```
#### deixará os comits (das duas pessoas) em ordem cronológica, e assim que digitado o comando acima, o `VSCode` ja vai apontar os conflitos que o Git encontrou, e com isso teremos três opções dentro do `VSCode`:
#### **Accept Both Changes**: aceitar ambas alterações;
#### **Accept Incomming Change**: Aceita as altarações que eu(no caso) fiz;
#### **Accept Current Change**: vai aceitar as alterações feitas na `branch` principal. Depois de escolher a opçao que melhor for, digite:
```git
git status
```
#### para ver as alterações feitas, na sequencia digite:
```git
git add .
```
#### na sequencia digite:
```git
git rebase --continue
```
#### basicamente ele vai criar um commit da alteração, agora digite:
```git
wq
```
#### após isso ele vai concluir listando os conflitos que foram resolvidos.Agora vamos c=voltar pra branch principal digitando:
```git
git checkout -
```
#### agora digite
```git
git merge "nome da branch"
```
#### E está concluido!