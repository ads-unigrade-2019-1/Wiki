# GRASPs e GoFs: API

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 20/05/2019 | 1.0  | Adicionando Factory Method | Gabriel Carvalho |

## Sumário
[1. Introduçao](#1-introducao) <br>
[2. GoFs - Criacionais](#2-gofs-criacionais) <br>

# Introdução


# GoFs Criacionais

## Factory Method

Factory Method é um padrão de projeto criacional que nos permite abstrair detalhes de implementação de criação de objetos do mundo externo. Express faz isso exportando apenas o construtor.

A função do framework que faz a criação da aplicação:  

[![Factory - Function](img/api-factory-func.png)](img/api-factory.png)

Importação e chamada da função na API:

[![Factory - Declaration](img/api-factory.png)](img/api-factory.png)

