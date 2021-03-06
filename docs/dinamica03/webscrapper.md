# Diagramas WebScrapper

## Histórico de revisões

|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|15/04/2019|   0.1    | Criação do documento       |   Daniel Maike  |
|15/04/2019|   0.2    | Adição do tópico de introdução e referências       |   Daniel Maike  |
|15/04/2019|   0.3    | Adição do diagrama de classes do MWScanner     |   Daniel Maike  |
|15/04/2019|   0.4    | Adição do diagrama de classes da conexão com o banco de dados     |   Joberth Rogers |
|15/04/2019|   0.5    | Adição do diagrama geral do WebScrapper     |  Daniel Maike e Joberth Rogers |
|15/04/2019|   0.6    | Adição da versão 2.0 dos diagramas MWScanner e geral do WebScrapper     |  Daniel Maike |
|16/04/2019|   0.7    | Adição da versão 3.0 dos diagramas MWScanner e geral do WebScrapper     |  Daniel Maike |
|23/04/2019|   0.8    | Adição das novas versões dos diagramas de classes do WebScrapper     |  Daniel Maike e Joberth Rogers |
| 26/04/2019 | 0.9 | Adicionando zoom nas imagens ao clicar | Joberth Rogers |
|26/06/2019|   1.0    | Adição da nova versão dos diagramas de classe do MWScanner     |  Daniel Maike |

## Sumário

[1. Introdução](#1-introducao) <br>
[2. Diagramas UML](#2-diagramas-uml) <br>
[3. Referências](#3-referencias)

## 1. Introdução

Em programação, um diagrama de classes é uma representação da estrutura e relações das classes que servem de modelo para objetos. Podemos afirmar de maneira mais simples que seria um conjunto de objetos com as mesmas características, assim saberemos identificar objetos e agrupá-los, de forma a encontrar suas respectivas classes. Na Unified Modeling Language (UML) em diagrama de classe, uma classe é representada por um retângulo com três divisões, são elas: O nome da classe, seus atributos e por fim os métodos.
Com o diagrama de classes foram representadas as classes do WebScrapper que é composto dos pacotes MWScanner e o de conexão com o banco de dados com os dados extraídos pelo MWScanner.

## 2. Diagramas UML

### Diagrama de classes MWScanner

O diagrama representa as classes do MWScanner, responsável por extrair os dados do Matrícula Web de Campus, Departamentos, Disciplinas, Ofertas das Disciplinas, Cursos e Habilitações.

#### Versão 1.0

[![mwscanner](img/MWScanner.png)](img/MWScanner.png)

#### Versão 2.0

[![mwscannerv2](img/MWScannerv2.jpg)](img/MWScannerv2.jpg)

#### Versão 3.0

[![mwscannerv3](img/MWScannerv3.jpg)](img/MWScannerv3.jpg)

#### Versão 4.0

[![mwscannerv4](img/MWScannerv4.jpg)](img/MWScannerv4.jpg)

#### Versão 5.0

[![mwscannerv5](img/MWScannerv5.png)](img/MWScannerv5.png)

### Diagrama de classes da conexão com o banco

O diagrama representa as classes da conexão com o banco de dados, responsável por tratar e preparar os dados extraídos pelo MWScanner para serem enviados ao banco de dados.

#### Versão 1.0

[![bancoconnection](img/umlconexaobanco.png)](img/umlconexaobanco.png)

#### Versão 2.0

[![bancoconnectionv2](img/umlconexaobancov2.jpg)](img/umlconexaobancov2.jpg)

#### Versão 3.0

[![bancov3](img/bancov3.png)](img/bancov3.png)

### Diagrama geral do WebScrapper

O diagrama representa o funcionamento geral do WebScrapper. A main executa o WebScrapper.

#### Versão 1.0

[![geral](img/scannerEBanco.png)](img/scannerEBanco.png)

#### Versão 2.0

[![geralv2](img/scannerEBancov2.jpg)](img/scannerEBancov2.jpg)

#### Versão 3.0

[![geralv3](img/scannerEBancov3.jpg)](img/scannerEBancov3.jpg)

#### Versão 4.0

[![geralv4](img/scannerEBancov4.jpg)](img/scannerEBancov4.jpg)

#### Versão 5.0

[![geralv5](img/geralv5.png)](img/geralv5.png)

## 3. Referências

* <https://online.visual-paradigm.com/tutorials/package-diagram-tutorial/> <br>
* <https://www.devmedia.com.br/orientacoes-basicas-na-elaboracao-de-um-diagrama-de-classes/37224> <br>
* <https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-package-diagram/> <br>