# GRASPs e GoFs: App

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 15/05/2019  | 1.0   | Introdução sobre os GoF's criacionais  |  Guilherme Aguiar|
| 19/05/2019  | 2.0   | Padrões Singleton do projeto  |  Guilherme Aguiar|
| 20/05/2019  | 3.0   | Grasp Especialista  |  Guilherme Aguiar|

## GOFs utilizados
[1. Singleton](#singleton-) <br>
[2. Builder](#builder) <br>
[3. Composite](#composite) <br>
[4. Adapter](#adapter) <br>
[5. Observer](#observer) <br>

## GRASPs utilizados
[1. Controller](#controller) <br>


## Singleton
O objetivo do Singleton é permitir a criação de uma única instância de uma classe e fornecer um modo para recuperá-la.
Esse padrão de projeto foi implementado nas camadas dos controladores da nossa arquitetura MVC. Os controllers são instanciados e utilizados pontualmente de maneira similar, em chamadas assíncronas e em fragments, que manipulam a interface.

#### Subjects Controller
Controller responsável por retornar a lista de todas matérias da API.
[![Singleton - SubjectsController](img/singleton_1.png)](img/singleton_1.png)

#### Classes Controller
Controller responsável por retornar a lista de todas turmas da API.
[![Singleton - ClassesFragment](img/singleton_2.png)](img/singleton_2.png)

#### TimeTables Controller
[![Singleton - ClassesFragment](img/singleton_3.png)](img/singleton_3.png)

## Builder
O padrão Builder não foi implementado manualmente, porém o Android faz uso desse para padrão a geração de janelas de alerta.

## Composite
Grande parte dos elementos gráficos do Android herdam de uma classe chamada "View". Em uma tela específica do aplicativo se tem layouts(que herdam da View), compostos por outros objetos gráficos, como botões e listas.

## Adapter
Como parte da arquitetura Android, os adapter são responsáveis por modificar os elementos gráficos de uma lista. Uma lista básica pode receber strings, porém o adapter pode modificá-la para receber outros itens, como: imagens, checkbox etc.

## Observer
O padrão observer foi implementado por meio dos listeners. Os listeners são métodos que aguardam a interação usuário com algum elemento da tela, normalmente butões, e executam ações após essa interação.

## Controller
Os controllers do app são responsáveis por guardar as funções mais pesadas e de interação com a api. Dessa forma, a manutenção e execução de testes é facilitada. 





