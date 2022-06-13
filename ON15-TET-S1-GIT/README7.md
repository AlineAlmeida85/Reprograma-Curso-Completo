## **Reset** e **Diff**

### Como podemos voltar em estados anteriores ou resetar os nossos erros?

#### Para voltar o arquivo para antes da edição utilizamos o comando:
```git
git checkout nome_arquivo
```
___
#### Para ver as modificações em um arquivo utilizamos o comando:
```git
git diff nome_arquivo
```
___
#### Para voltar arquivos `staged` utilizamos o comando:
```git
git reset HEAD nome_arquivo
```
___
#### Para voltar arquivos que já estão em um `commit` utilizamos o comando:

```git
git reset --soft id_commit_anterior
```
```git
git reset --mixed id_commit_anterior
```
```git
git reset --hard id_commit_anterior
```
___
```git
git revert id_commit
```
#### Para desfazer um commit mantendo o histórico
___
