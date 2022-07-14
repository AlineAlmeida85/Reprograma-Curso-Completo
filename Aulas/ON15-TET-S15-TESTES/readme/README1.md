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
### *TESTE MANUAL*
#### Testar manualmente a aplicação, de acordo com as especificações, **avaliando o design, a funcionalidade e o desempenho.**
- Testes exploratórios
  - Teste Ad-Hoc
- Testes de usabilidade
___
### *TESTE AUTOMATIZADO*
#### Testes automatizados são scripts que utilizam as **entradas e saídas de um software para simular um usuário ou um sistema.** Desta forma, podemos ter uma grnde área de cobertura dos testes que pode ser automatizada sem implicar em grandes custos.
___
### *TESTE DE PERFORMANCE*
#### **Ajuda a descobrir a velocidade, escalabilidade e estabilidade de desempenho da aplicação.** Simulando fluxos simultâneos de pessoas utilizando o sistema.
___
### *TESTE DE ACEITAÇÃO*
#### O teste de aceitação é a ação de teste final antes da implementação do software. A meta do teste de aceitação é **verificar se o software está pronto e pode ser utilizado pelos usuários**, para desempenhar as funções e tarefas para as quais o software foi construído.
#### É um Test Drive!
##### Obs: aceitação pela equipe.
___
### *TESTE DE REGRESSÃO VISUAL*
#### Analiza a estrutura visual da aplicação e **tenta identificar,** de acordo com as regras de negócios, **se a página está sendo renderizada de forma correta.**
___
### *TESTE DE API`S*
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
 └─ Funcional -> Garantir que o endpoint funciona ou apresenta os resultados de falha esperados
 ```
___
### *TESTE DE UNIDADE*
#### Um teste unidade basicamente `é o teste da menor parte testável de um programa`.
___
### *TESTE DE INTEGRAÇÃO*
#### `Testa os caminhos de comunicação entre diferentes partes do módulos`, verificando se estão funcionando corretamente juntos.
___
### *TESTE DE PONTA A PONTA (END TO END)*
#### Testes de ponta a ponta `envolve todos os processos que fazem o programa funcionar`.

___
## `PIRÂMIDE DE TESTES`
#### Representa os tipos de testes que devem ser incluídos em um conjunto de testes automatizados.
<p align="center">
  <img alt="foto" title="foto" src="https://supremotribunalfederal.gitlab.io/images/politicas/piramide.png"/>
</p>
<p align="center">
  <img alt="foto" title="foto" src="https://lh5.googleusercontent.com/X-68m7pb9ZTvyya78WrLIwz9331GbhAHFziKDHaW-fXdqAxCMZFjmlWx1GM0TepbuvZn9ARWvotBn05WmWsNznDjxFmkslFab7IKxh8ghhPdM4t-f380m--Hbx4gqejRkYVh1jwZ"/>
</p>

___
## `Benefício da automação de testes`
- Repetição e Volume
- Produtividade
- Reduzir a chance de termos erros
- Reduz a quantidade de esforço que seria realizado em testes manuais
- Testes automatizados são reutilizados, poupam recursos humanos
- Redução de custos, ganho na qualidade
- Confiabilidade e robustez do código

#### E como funciona?
- Garantir boa funcionalidade da aplicação (o teste é um contrato)
- Construção de ambiente automatizado
- Base de dados automatizada (input de massa de dados para testes)
- Segregação de aplicação de testes (pré submit: teste de unidade, teste de
integração no código; post submit: testes gráficos)
- Automatização dos testes críticos
- Testabilidade como parte da aplicação
- Confiança nas ferramentas de teste
- Infraestrutura
- Um projeto para investir a longo prazo
___
## `Como funciona a automação de testes`

<img alt="foto" title="foto" src="http://assets.stickpng.com/images/62a765c8bd73a4af5c5d4fbc.png" width=80/>

#### Estrutura de teste JavaScript construída em cima do Jasmine e mantida pela Meta. É utilizado no React, assim como ferramenta de teste unitário para diversas plataformas JavaScript como Node e Redux, e até mesmo plataformas em TypeScript como Angular e Ionic.

___
### `Mas, e o TDD?`
#### `Test-driven development` -> **Desenvolvimento orientado a testes**
#### `DDD` (`Domain Driven Design`) -> **Desenvolvimento Guiado Por Design** ou **Desenvolvimento Orientado a Domínio**
___
### `Mas, e o TDD?`
#### **Testes unitários** (ferramenta)
#### **TDD** (técnica)
#### `“Primeiro faça, depois faça certo e, então, faça melhor.”`
 