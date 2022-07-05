## `O que é Automação de Testes?`
___


#### **Escrever scripts para que o computador execute testes de maneira automatizada, utilizando um Framework.**
#### Reduz o tempo de execução dos testes, diminuindo o impacto de algum cenário esquecido virar um bug, uma falha ou um prejuízo para a empresa.
#### Controla:
- A execução do teste de software;
- A comparação dos resultados esperados co os resultados reais;
- A configuração das pré-condições de teste;
- E outras funções de controle e relatório de teste.

## `Tipos de Testes`
___


|Funcional | Estrutural | Não-Funcional | Mudança |
|:-------: | :--------: | :-----------: | :-----: |
|Teste de Sistema | Teste de Unidade | Teste de Usabilidade | Teste de Confirmação |
| Teste de Aceitação | Teste de Integração | Teste de Carga | Teste de Regressão |
|   |   | Teste de Segurança |  |

___
### *Teste Manual*
#### Testar manualmente a aplicação, de acordo com as especificações, **avaliando o design, a funcionalidade e o desempenho.**
- Testes exploratórios
  - Teste Ad-Hoc
- Testes de usabilidade
___
### *Teste Automatizado*
#### Testes automatizados são scripts que utilizam as **entradas e saídas de um software para simular um usuário ou um sistema.** Desta forma, podemos ter uma grnde área de cobertura dos testes que pode ser automatizada sem implicar em grandes custos.
___
### *Teste de Performance*
#### **Ajuda a descobrir a velocidade, escalabilidade e estabilidade de desempenho da aplicação.** Simulando fluxos simultâneos de pessoas utilizando o sistema.
___
### *Teste de Aceitação*
#### O teste de aceitação é a ação de teste final antes da implementação do software. A meta do teste de aceitação é **verificar se o software está pronto e pode ser utilizado pelos usuários**, para desempenhar as funções e tarefas para as quais o software foi construído.
#### É um Test Drive!
##### Obs: aceitação pela equipe.
___
### *Teste de Regressão Visual*
#### Analiza a estrutura visual da aplicação e **tenta identificar,** de acordo com as regras de negócios, **se a página está sendo renderizada de forma correta.**
___
### *Testes de API'S*
#### Valida se o comportamento está correto:
- Requisição e Resposta
- Status Code
- Dados
```
API
 |
 ├─ Health Check -> Garantir que o endpoint está respondendo
 |
 ├─ Contrato -> Garantir que o endpoint não teve seus atributos alterados
 |
 ├─ Aceitação -> Garantir que um conjunto de endpoints funcionam como na UI
 |
 ├─ Funcional -> Garantir que o endpoint funciona ou apresenta os resultados de falha esperados
 ```
 