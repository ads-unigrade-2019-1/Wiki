# Padrões Emergentes: App

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 29/06/2019 |  1.0 | Sumário e Padrão ViewHolder | Gabriela Medeiros |

## Padrões Emergentes Utilizados
[1. ViewHolder](#viewholder) <br>
[2. MVVM](#mvvm) <br>
[2. MVP](#mvvm) <br>

## ViewHolder
ViewHolder é um padrão que busca o armazenamento de views quando em sua primeira utilização para que em posterior necessidade de uso serem reutilizadas. O padrão aumenta a performance da aplicação ao impedir a repetição excessiva de consultas à view, oferecendo a possibilidade um único acesso a ela.

#### Subject List Adapter

[![ViewHolder - SubjectListAdapter](img/viewHolder_1.png)](img/viewholder_1.png)

#### Class List Adapter

[![ViewHolder - ClassListAdapter](img/viewHolder_2.png)](img/viewHolder_2.png)

#### Timetable List Adapter

[![ViewHolder - TimetableListAdapter](img/viewHolder_3.png)](img/viewHolder_3.png)

## MVVM
MVVM (_Model View ViewModel_) é um _pattern_ específico para a arquitetura do WPF E Silverlight. 
O MVVM busca estabelecer uma modularização entre a classe de negócio (modelos, serviçoes externos e acesso ao banco de dados) e a View, que é o meio de interação do usuário. A ModelView faz a comunicação entre a View e a Model, sendo que a View não possui conexão direta com a Model e a Model não possui conexão direta com a View.

## MVP
O MVP (_Model View Presenter_) é uma derivação do padrão MVC (_Model View Controller_) onde o _Presenter_ é o mediador entre a Model e a View, a _View_ é reponsável por tratar as interações do usuário e a Model define o modelo de dados. 