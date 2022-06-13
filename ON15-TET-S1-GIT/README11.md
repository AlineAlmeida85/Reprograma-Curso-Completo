## **Workflows** com Git

### Workflow é um termo inglês que significa fluxo de trabalho. Com os workflows do git trabalhamos de maneira mais consistente e produtiva.

#### Workflows com Git
#### **Centralized**: Todos os desenvolvedores trabalham na branch main. Para obter as modificações de um repositório remoto realizando o rebase utilizamos o comando: 
```git
git pull origin main --rebase
```
#### e 
```git
git push origin main
```
___
#### **Feature Branch**: Todos os desenvolvedores trabalham com novos recursos utilizando uma nova branch
#### **Gitflow**: Todos os desenvolvedores trabalham com um modelo estrito de branches projetado em torno do lançamento do projeto