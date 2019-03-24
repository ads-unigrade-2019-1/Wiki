# Arquitetura

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|23/03/2019|   0.1    | Iniciando o documento           |   Guilherme Aguiar  |
|24/03/2019|   0.2    | Adição do tópicos sumário e API |   Gabriel Carvalho |
|24/03/2019|   0.3    | Adição das referências          |   Gabriel Carvalho  |
|24/03/2019|   0.4    | Correção de sumário e adição de visão geral |   Geovana Ramos |

-------------------------

## Sumário
[1. Visão Geral](#1-visão-geral) <br>
[2. App](#2-app) <br>
[3. API](#3-api) <br>
[4. Banco de Dados](#4-banco-de-dados)<br>
[5. Referências](#5-referências)<br>

## 1. Visão Geral
![VisaoGeral](img/GeovanaVisaoArquitetura.png)

O sistema será composto pelo aplicativo Android, duas APIs e um banco de dados. O app irá fazer requisições à API Node para recuperar as disciplinas e montar as grades, a qual irá recuperar dados do banco. A API WebScraper irá varrer o matrícula web e salvar os dados no banco de dados MongoDB.

## 2. App
### 2.1 Tecnologias

## 3. API
A API será desenvolvida utilizando os princípios REST (Representational State Transfer), que se comunica por meio do protocolo HTTP (Hypertext Transfer Protocol), onde é possível enviar e receber dados utilizando os métodos GET, POST, PUT e DELETE.

![API](https://happycoding.io/tutorials/java-server/images/rest-api-1.png)

### 3.1 Tecnologias

![Node_express](https://cdn-images-1.medium.com/max/730/1*d2zLEjERsrs1Rzk_95QU9A.png)

Para o desenvolvimento da nossa API, iremos utilizar Node.js e o framework Express.js. Node foi escolhido por ser possível trabalhar com requisições assíncronas, fazendo com que a API ganhe mais performance. Express.js foi escolhido por facilitar o desenvolvimento da API utilizando Node.js.

![Express_diagram](https://binariks.com/wp-content/uploads/2017/11/express-js-840x502.png)

## 4. Banco de Dados
### 4.1 Tecnologias


### 5. Referências
* Reunião feita na aula do dia 22/03/2019.
* [Mapa Mental feito na aula](dinamica01/mapamental.md)
* [Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm). Fielding, Roy Thomas.
* [REST: Princípios e boas práticas](https://blog.caelum.com.br/rest-principios-e-boas-praticas/). Ferreira, Rodrigo.
