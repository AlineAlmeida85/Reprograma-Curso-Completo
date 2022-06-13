## ✔️`Configuração` do `Git`
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
#### 
___
## Ciclo de Vida dos Arquivos e Commits

#### Como gerar um novo estado (ou versão) do nosso código?
#### O Git possui 4 ciclos de vida para os arquivos:
#### `untracked (estado inicial)`: o git ainda não conhece a existência do arquivo em nenhuma versão.
#### `unmodified`: ficam os arquivos que não sofreram nenhuma alteração em relação à última versão
#### `modified`: ficam os arquivos que sofreram alteração em relação à última versão
#### `staged`: ficam os arquivos que estão prontos para serem inseridos na nova versão
___

### Os estados:
#### os arquivos inicialmente ficam em estado **untracked**, utilizando o comando 
```git
git add .
```
#### os arquivos passam para o estado **staged**, para proseguirmos com o avanço dos arquivos utilizamos o comando:
```git
git commit -m "sua mensagem"
```
#### e então os arquivos passam para o estado **unmodified**, e quando fazemos uma nova modificação, esses arquivos mudam para o estado **modified**
___

#### O **commit** é utilizado para avisar o `git` que queremos gerar um novo estado com os arquivos em **`staged`**

#### Caso queira voltar os arquivos para o estado **untracked**, digite o comando:
```git
git reset
```
___
#### Para consultar o status dos arquivos utilizamos o comando:
```git
git status
```
___
#### Para alterar consultar commits utilizamos o comando
```git
git log
```
___