# GRASPs e GoFs: App

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 15/05/2019  | 1.0   | Introdução sobre os GoF's criacionais  |  Guilherme Aguiar|
| 19/05/2019  | 2.0   | Padrões Singleton do projeto  |  Guilherme Aguiar|
| 20/05/2019  | 3.0   | Grasp Especialista  |  Guilherme Aguiar|
| 25/06/2019  | 3.1   | Adicionando GoFs e GRASPs  |  Geovana Ramos |
| 26/06/2019  | 3.2   | Adicionando imagens  |  Gabriela Medeiros|

## GOFs utilizados
[1. Singleton](#singleton-) <br>
[2. Builder](#builder) <br>
[3. Composite](#composite) <br>
[4. Adapter](#adapter) <br>
[5. Observer](#observer) <br>

## GRASPs utilizados
[1. Controller](#controller) <br>


## Singleton
O objetivo do Singleton é permitir apenas uma instanciação de classe e fornecer um método para recuperá-la.
Esse padrão de projeto foi implementado nas camadas dos controladores (_controller_) no contexto da arquitetura MVC. Os controllers são instanciados e utilizados pontualmente de maneira similar, em chamadas assíncronas e em fragments, que manipulam a interface.
[![Singleton](img/singleton10.png)](img/singleton10.png)


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
[![Builder](img/builder1.gif)](img/builder1.gif)

## Composite
Grande parte dos elementos gráficos do Android herdam de uma classe chamada "View". Considerando que cada tela do aplicativo possui layouts compostos por outros objetos gráficos, como botões e listas, e que ambos são "_views_", podemos observar um _composite_ em tal relação.
[![Composite](img/composite1.png)](img/composite1.png)

## Adapter
Como parte da arquitetura Android, os adapter são responsáveis por modificar os elementos gráficos de uma lista. Uma lista básica pode receber exclusivamente strings, porém o adapter pode modificá-la para receber outros tipos e combinação de dados e _views, como: imagens, checkbox, botões, etc.
[![Adapter](img/adapter1.png)](img/adapter1.png)

## Observer
O padrão observer foi implementado por meio dos listeners. Os listeners são métodos que aguardam a interação do usuário com algum elemento da tela (botões, _checkbox_, _spiners_, entre outros) para executar os comandos já determinados.
[![Observer](img/observer1.jpg)](img/observer1.jpg)

## Controller
Os controllers do app são responsáveis por guardar as funções mais pesadas e de interação com a api. Dessa forma, a manutenção e execução de testes é facilitada.
