# Paralelo com Outras Metodologias

## Histórico de revisões

|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|04/04/2019|   0.1    | Criação do documento       |   Daniel Maike  |
|04/04/2019|   0.2    | Adicionados tópicos Introdução, SCRUM e KanBan       |   Daniel Maike  |
|04/04/2019|   0.3    | Adicionados tópicos RUP e XP      |   Guilherme Deusdará  |

## Sumário

[1. Introdução](#1-introducao) <br>
[2. SCRUM](#2-scrum) <br>
[3. Kanban](#3-scrum) <br>
[4. RUP](#4-rup) <br>
[5. XP](#5-extreme-programming-xp) <br>
[6. Referências](#6-referencias)

## 1. Introdução

Metodologia é o campo em que se estuda os melhores métodos praticados em determinada área para a produção do conhecimento.
Com o objetivo de alcançar a maior produtividade da equipe, levando em consideração a duração da disciplina e os diferentes horários disponíveis dos membros da equipe para dedicação exclusiva ao projeto, foi feito um paralelo entre metodologias muito utilizadas.

## 2. SCRUM

Scrum é uma metodologia ágil para gestão e planejamento de projetos de software.
No Scrum, os projetos são dividos em ciclos chamados de Sprints. O Sprint representa um Time Box dentro do qual um conjunto de atividades deve ser executado. As funcionalidades a serem implementadas em um projeto são mantidas em uma lista que é conhecida como Product Backlog. No início de cada Sprint, faz-se um Sprint Planning Meeting, uma reunião de planejamento na qual os itens do Product Backlog são priorizados e a equipe seleciona as atividades que ela será capaz de implementar durante o Sprint que se inicia. As tarefas alocadas em um Sprint são transferidas do Product Backlog para o Sprint Backlog. A cada dia de uma Sprint, a equipe faz uma breve reunião, chamada Daily Scrum.
Ao final de um Sprint, a equipe apresenta as funcionalidades implementadas em uma Sprint Review Meeting. Finalmente, faz-se uma Sprint Retrospective e a equipe parte para o planejamento do próximo Sprint. Assim reinicia-se o ciclo.

### 2.1 Recursos utilizados

Sprints: Time Box dentro do qual um conjunto de atividades deve ser executado; <br>

Product Backlog: Basicamente, é uma lista com tudo que se deseja no produto, ou seja, todas as funcionalidades que o produto deve possuir. Durante o projeto, pode ser alterado de acordo com o aumento do entendimento sobre o projeto; <br>

Sprint Backlog: Lista de funcionalidades a serem implementadas até o término da sprint; <br>

Reunião de planejamento e revisão da sprint: Ocorre no início da sprint e tem como objetivo organizar o funcionamento da sprint com uma breve análise do que foi alcançado na sprint anterior; <br>

Product Owner: É o membro da equipe que define histórias e prioriza o backlog de um produto ou projeto. É o responsável por manter a integridade conceitual das novas funcionalidades, bugs ou melhorias, para que essas sigam uma visão definida para esse produto ou projeto;

## 3. Kanban

Kanban é um termo de origem japonesa e significa literalmente “cartão” ou “sinalização”. Este é um conceito relacionado com a utilização de cartões (post-it e outros) para indicar o andamento dos fluxos de produção em empresas de fabricação em série. A utilização de um sistema Kanban permite um controle detalhado de produção com informações sobre quando, quanto e o que produzir.

### 3.1 Recursos utilizados

O grupo está utilizando o quadro de tarefas por meio do GitHub para uma melhor organização, com as seguintes colunas: To Do, In progress, Review in progress, Review approved e Done. Com o objetivo de definir quais funcionalidades estão no Backlog da Sprint, bem como aquelas que estão sendo feitas, revisadas ou concluídas. Disponível em: <https://github.com/orgs/ads-unigrade-2019-1/projects/1>

## 4. RUP

O RUP é um processo de desenvolvimento de software. Ele engloba as ações necessárias para transformar um conjunto de requisitos do cliente em um sistema de software. O RUP combina os ciclos de vida iterativo e incremental de forma que cada entrega do software em um ciclo agrega mais valor ao produto em relação ao ciclo anterior. A grande vantagem em desenvolver um grande sistema usando um processo incremental é a diminuição do risco, pois cada entrega pode ser avaliada e o passe seguinte alinhado com os objetivos do cliente, que nem sempre permanecem constantes durante o desenvolvimento de um projeto.

As fases do RUP são:

* Fase de Concepção: ênfase no escopo do sistema.
* Fase de Elaboração: ênfase na arquitetura.
* Fase de Construção: ênfase no desenvolvimento. 
* Fase de Transição: ênfase na implantação. 

## 4.1. Recursos utilizados

* A pré-fase do projeto será baseada nas fases de Concepção e Elaboração. Serão utilizados os seguintes elementos da fase de Concepção: 
    * definição e documentação o escopo, 
    * elicitação, modelagem dos requisitos, que serão transformados em histórias de usuário
* Da fase de Elaboração será construída a documentação a respeito da arquitetura como diagrama de classes, de estados, entre outros.

## 5. eXtreme Programming (XP)

Programação extrema (do inglês eXtreme Programming), ou simplesmente XP, é uma metodologia ágil para equipes pequenas e médias e que irão desenvolver software com requisitos vagos e em constante mudança. Para isso, adota a estratégia de constante acompanhamento e realização de vários pequenos ajustes durante o desenvolvimento de software.

Os cinco valores fundamentais da metodologia XP são: comunicação, simplicidade, feedback, coragem e respeito. A partir desses valores, possui como princípios básicos: feedback rápido, presumir simplicidade, mudanças incrementais, abraçar mudanças e trabalho de qualidade.

Dentre as variáveis de controle em projetos (custo, tempo, qualidade e escopo), há um foco explícito em escopo. Para isso, recomenda-se a priorização de funcionalidades que representem maior valor possível para o negócio. Desta forma, caso seja necessário a diminuição de escopo, as funcionalidades menos valiosas serão adiadas ou canceladas.

A XP incentiva o controle da qualidade como variável do projeto, pois o pequeno ganho de curto prazo na produtividade, ao diminuir qualidade, não é compensado por perdas (ou até impedimentos) a médio e longo prazo.

## 5.1. Recursos utilizados

* Pair Programming: é a programação em par/dupla num único computador. Desta forma, cada issue será feita por duas pessoas, evitando e diminuindo assim a possibilidade de defeitos. Com isto busca-se sempre a evolução da equipe, melhorando a qualidade do código fonte gerado.
* Sustainable Pace: Trabalhar com qualidade, buscando ter ritmo de trabalho saudável.
* Coding Standards (Padronização do código): A equipe de desenvolvimento precisa estabelecer regras para programar e todos devem seguir estas regras.
* Continuous Integration: Sempre que a equipe produzir uma nova funcionalidade, nunca esperar uma semana para integrar à versão atual do sistema. Isto só aumenta a possibilidade de conflitos e a possibilidade de erros no código fonte. Integrar de forma contínua permite saber o status real da programação.

## 6. Referências

* <https://www.significados.com.br/kanban/> <br>
* <https://www.desenvolvimentoagil.com.br/scrum/> <br>
* <https://www.desenvolvimentoagil.com.br/xp/> <br>
* <https://github.com/2018-2-Desenho/CabecaVoleiJoelhoPe> <br>
* <http://www.metodoagil.com/scrum/> <br>
* <https://www.significados.com.br/metodologia/> <br>
