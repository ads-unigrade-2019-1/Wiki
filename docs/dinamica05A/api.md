# GRASPs e GoFs: API

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 20/05/2019 | 1.0  | Adicionando Factory Method | Gabriel Carvalho |
| 20/05/2019 | 1.1  | Relacionando com GRASP | Ezequiel Oliveira |

## Sumário
<ul>
    <li> [1. Introdução](#introdução) </li>
    <li> [2. GoFs - Criacionais](#gofs-criacionais) </li>
    <ul>
       <li> [2.1 Factory Method](#factory-method) </li>
    </ul>
</ul>

## Introdução


## GoFs Criacionais

### Factory Method

Factory Method é um padrão de projeto criacional que nos permite abstrair detalhes de implementação de criação de objetos do mundo externo. Express faz isso exportando apenas o construtor.

A função do framework que faz a criação da aplicação:  

[![Factory - Function](img/api-factory-func.png)](img/api-factory.png)

Importação e chamada da função na API:

[![Factory - Declaration](img/api-factory.png)](img/api-factory.png)

### GRASP's Relacionados:

#### Information Expert:

O trecho de codigo pode-se notar que o express consegue instanciar seu objeto único, considerando-o especialista pois ele tem a responsabilidade de gerar um objeto usado ao longo do codigo.

