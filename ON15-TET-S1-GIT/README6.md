## ✔️ **Instalação** do **Git**
___
#### Baixe a versão de acordo com o sistema operacional
___

### Configurações básicas

```git
git config --global init.defaultBranch main
```
#### setar as configurações, definição de  **branch** principal, ou seja, sempre que eu inicializar um projeto, será setado com o nome de branch principal **main**
___


```git
git config –global user.name "seu nome"
```
#### definição do **nome** da pessoa que irá versionar o projeto
___

```git
git config –global user.email "seuemail@seuemail.com"

```
#### definição do **email** da pessoa que irá versionar o projeto
___

```git
git config --list
```
#### saber se as configurações estão corretas
___
```git
git config --global --unset user.name "Nome"
```
#### 
___
```git
git config --global --unset user.email “nome@email.com”
```
