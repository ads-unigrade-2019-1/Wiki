# Modelos Dinâmicos: App

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|28/04/2019|0.1|   Adicionado diagramas de sequência  |  Gabriela Medeiros  |
|28/04/2019|0.2|   Corrigindo sumário/links e adicionando diagrama de estado  |  Geovana Ramos  |
|28/04/2019|0.3|   Adicionado diagrama 2 de Colaboração  |  Rafael Braganca  |

## Sumário
[1. Diagramas de Sequência](#1-diagramas-de-sequencia) <br>
[2. Diagrama de Estado](#2-diagrama-de-estados) <br>
[2. Diagrama de Colaboração](#2-diagrama-de-colaboração) <br>

## 1. Diagramas de Sequência

### Fluxo Geral do APP

[![UML de Sequência - Fluxo geral do app](img/appSequenceDiagram1.png)](img/appSequenceDiagram1.png)

### Fluxo de Carregamento da Lista de Matérias

[![UML de Sequência - Carregamento da tela de matérias](img/appSequenceDiagram2.png)](img/appSequenceDiagram2.png)

## 2. Diagrama de Estados
Esse diagrama representa os ciclos de vida de uma aplicação Android. No app UniGrade há uma Activity e seis Fragments. Todos seguem o ciclo de vida descrito no diagrama, porém está sendo representado apenas uma Activity que contém um Fragment. Esse Fragment pode ser qualquer um dos seis existentes.
[![UML de Estado - Android](img/umlstateandroid.png)](img/umlstateandroid.png)

## 3. Diagrama de Colaboração
Assim como o diagrama de sequência, esse diagrama mostra de uma forma mais simplificada a interação entre objetos e partes através de mensagens sequenciais

### Fluxo Geral do APP
[![UML de Colaboração - Carregamento da tela de matérias](img/appCommunicationDiagram1.png)](img/appCommunicationDiagram1.png)

### Fluxo de Carregamento da Lista de Matérias
[![UML de Colaboração - Carregamento da tela de matérias](img/appCommunicationDiagram2.png)](img/appCommunicationDiagram2.png)
