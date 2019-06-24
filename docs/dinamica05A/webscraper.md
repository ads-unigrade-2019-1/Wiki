# GRASPs e GoFs: WebScraper

## Histórico de revisões
|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|  20/05/2019 |  0.1 | Iniciação do documento  |  Joberth Rogers|

## Sumário
[1. Introdução](#1-introducao) <br>
[2. Singleton](#2-singleton) <br>
[3. Builder](#3-builder) <br>
[4. Padrões GRASP](#4-padroes-grasp) <br>
[5. Referências](#5-referencias) <br>

# 1. Introdução

<p style="text-align: justify">Como apresentado em dinâmicas passadas, o script do mwscanner foi começado nas primeiras sprints por ser uma das vertentes do projeto crucial para o andamento final do Unigrade, onde seu objetivo é coletar todos os dados relacionados a vida acadêmica da Universidade de Brasília. Por ser algo tão breve e importante para ser feito logo, o grupo entrou em um concesso de apenas se preocupar em criar o script de forma otimizada e funcional, não se importando com a arquitetura e qualquer tipo de padrão, devido a conhecimentos ainda não ensinados pela professora, mas nas últimas sprints  esses conceitos foram absorvidos e relatados no decorrer das semanas. Como primeiro passo na dinâmica, o grupo se preocupou em aplicar padrões relacionados ao grupo de padrões criacionais, onde se tem o objetivo de saber como os objetos estão sendo criados, se sua instância é frequente  e  desnecessária em alguns caso, ou atribuição de responsabilidades de classes para outra de forma a desacoplar a arquitetura e melhorar a performance. Os padrões levantados e adequados ao Mwscanner foram: </p>

# 2. Singleton

<p style="text-align: justify">Esse padrão que por muitos autores até hoje é considerado como anti-pattern, para o script Mwscaner foi um fator que alavancou sua performance de forma muito considerável. Como o script faz a coleta de vários dados do Matrícula Web e salva todos no banco de dados não relacional, ao executar o script resultava em uma grande perda de performance na hora de salvar esses dados, devido à criação de uma instância do MongoDB a cada vez que uma nova divisão do Matrícula web era iniciada. Então foi necessário o uso do padrão singleton, para cuidar da criação de uma única instância no começo da execução do script. Aumentando a performance do programa e evitando a criação de objetos relacionados a conexão com o banco de dados de modo desnecessário. O código referente ao singleton está presente abaixo:</p>    

[![singleton-mwscanner](img/singleton_mwscanner.png)](img/singleton_mwscanner.png)

<p style="text-align: justify">Ao aplicar o padrão tivemos a queda no tempos 
de execução da build de: </p>

[![build_gitlab-mwscanner](img/build_gitlab1.png)](img/build_gitlab1.png)

<p>Para: </p>

[![build_gitlab-mwscanner](img/build_gitlab2.png)](img/build_gitlab2.png)

<p>Ou seja, o nível de satisfação do padrão foi ótimo na aplicação do script, obtendo
resultados muito favoráveis e destruído o gargalo na hora da conexão do banco. </p>

<p> Para verificar os links da build, acesse: <br>
  <a href="https://gitlab.com/ads-unigrade-2019-1/MWScanner/-/jobs/214912533"> https://gitlab.com/ads-unigrade-2019-1/MWScanner/-/jobs/214912533 </a> <br>
  <a href="https://gitlab.com/ads-unigrade-2019-1/MWScanner/-/jobs/203499362"> https://gitlab.com/ads-unigrade-2019-1/MWScanner/-/jobs/203499362 </a>
</p>

# 3. Builder
<p sytlr="text-align: justify">
Como abordado na definição, o padrão do tipo builder tem por objetivo tentar encapsular a lógica de construção dos objetos criados, devido a complexidade da criação deles, que em alguns casos podem ser muito alta. Portanto, esse padrão tenta isolar a forma que os passos da criação do objeto tomam, a fim de criar objetos de forma simples para a aplicação tornando o código e as estrutura mais agradável e de fácil manutenção (assim botando ordem ao caos). Exemplo de um trecho de código no mwscanner envolvendo builder: </p>

<br>

[![builderclass-mwscanner](img/builder.png)](img/builder.png)

# 4. Padrões GRASP

**G**eneral **R**esponsibility **A**ssignment **S**oftware **P**rinciples – Princípios Gerais do Software de Atribuição de Responsabilidade

Representam os princípios e o racicínio utilizado para atribuir responsabilidades de objetos que podem ser descritos de modo metódico, explicável e repetível.

O padrão GRASP **Criador**, em que se determina a responsabilidade da criação da instância de um objeto a uma classe, é visualizado nas classes do Builder do MWScanner, elas são responsáveis por criar instancias das classes em que elas possuem os dados, também é visualizado o padrão GRASP **Especialista**, com a atribuição de responsabilidade de criar instancia de classe nas classes do Builder.

O padrão GRASP **Invenção Pura** é uma classe que não representa um conceito no domínio do problema, especialmente criado para alcançar baixo acoplamento, alta coesão e o potencial de reutilização. Com isto é visualizado o GRASP **Invenção Pura** nos Mixins que são classes que não são classes exatamente necessárias no projeto mas que foram criadas para aumentar o potencial de reutilização pelas classes de extração de dados do Matricula Web, com isso, é visto o GRASP **Baixo Acoplamento** por diminuir o acoplamento com a distribuição de responsabilidades entre as classes e aumento da coesão (GRASP **Alta Coesão**) e do uso do GRASP **Especialista** com classes focadas em suas responsabilidades, classes que não realizam grande volume de trabalho.

O padrão GRASP **Indireção** é a utilização de uma classe intermediária para melhor distribuição das responsabilidades e evitando um acoplamento direto. É possível observar nas classes de salvamento dos dados, cada Collection possui uma classe em que pega os dados extraídos pelo Webscraper e os coloca na forma esperada a ser salva nas Collections do banco de dados MongoDB Atlas, cada classe é responsável por uma Collection e depois a classe saveData salva o que vem de cada classe para o banco de dados. Também possui uma Indireção entre as turmas e as disciplinas, para a classe de salvamento das discplinas não ficar com um grande volume de trabalho, foi criada uma classe para tratar das turmas e já devolver a classe das disciplinas da forma esperada. A **Indireção** também fortalece a responsabilidade de cada classe, divide as responsabilidades para não deixar grande volume de trabalho para cada classe. Com isto, também fortalece os GRASPS de **Alta Coesão**, **Baixo Acoplamento** e o **Especialista**, esses três colaboram um com o outro dentro do projeto.

# 5. Referências

* Slide padrões GOF - disciplina de Arquitetura e Desenho de Software da UnB-Gama - Professora: Milene Serrano