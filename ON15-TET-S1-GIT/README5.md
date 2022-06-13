## ✔️ **BRANCHES** 
### `Branches` criam uma linha alternativa no tempo para trabalharmos em paralelo, permitem trabalharmos de forma independente e colaborativa, podemos realizar alterações na nossa `branch` e somente depois de finalizar é que podemos então juntar essas modificações na `main`

___
#### Para consultar commits visualizando as ramificações utilizamos o comando:
```git
git log --graph
```
___
#### Para criar uma nova branch utilizamos o comando
```git
git branch nome_branch
```
___
#### Para alterar de branch utilizamos o comando
```git
git checkout nome_branch
```
___
#### Para unir duas branches utilizamos o comando
```git
git merge nome_branch
```
___
### Juntando a `branch` com a `main`.

#### Supondo que voce ja criou sua `branch` e ja concluiu as alterações no seu projeto, vamos publicá-las no GitHub.
#### Digite:
```git
git add .
```
#### para adicionar suas atualizações no estado atual. Agora vamos digitar:
```git
git commit -m "sua mensagem"
```
#### para commitar. Agora vamos jogar as atualizações digitando:
```git
git push origin "nome da branch"
```
#### Na sequencia digite:
```git
git checkout main
```
#### Agora digite:
```git
git merge branch
```
#### para juntar as atualizações, e por último vamos digitar:
```git
git push -u origin main
```
#### E pronto! Suas atualizações estarão disponíveis no repositório remoto.
