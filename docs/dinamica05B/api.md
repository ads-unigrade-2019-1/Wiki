# Padrões Emergentes: API

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)         |
|:--------:|:--------:|:----------------------:|:---------------------------:|
| 25/05/2019  | 0.1  | Criando introdução  | Guilherme Deusdará |
| 25/05/2019  | 0.1  | adicionando padrão Factory  | Guilherme Deusdará |

## Sumário
[1.Introdução](#1-Introdução) <br>
[2.Factory ](#2-factory) <br>

## 1. Introdução

O Express é uma framework de aplicações Web pada Node.js, que é minimalístico e flexível e fornece um conjunto robusto de recursos para aplicativos da Web e móveis.

Abaixo estão alguns padrões de projeto emergentes que podemos ver ao trabalhar com o Express.js

## 2. Factory

Este é um padrão de design simples e comum em JavaScript. Factory é um padrão de projeto *criacional* que nos permite abstrair detalhes de implementação de criação de objetos do mundo externo. Express faz isso exportando apenas o criadorf.

```
/**
 * Expose `createApplication()`.
 */
exports = module.exports = createApplication;
function createApplication() {
  var app = function(req, res, next) {
    app.handle(req, res, next);
  };
  ...
  return app;
}
```

E usar a Factory para criar uma aplicação expressa é tão simples quanto isto:

```
import express from 'express';
...
const app = express();
``` 
