# Explicação do Algorítimo 

## Histórico de revisões

|   Data   |  Versão  |        Descrição       |          Autor(es)          |
|:--------:|:--------:|:----------------------:|:---------------------------:|
|30/06/2019|    0.1   | Adicionando explicação | Guilherme Guy |

## Sumário

[1. Introdução](#1-introducao) <br>
[2. Algorítimo](#2-algoritimo) <br>
[3. Restrições](#3-restricoes) <br>
[4. Limitações](#3-limitacoes) <br>
[5. Referências](#3-referencias) <br>

## 1. Introdução

O algorítimo que monta as grades é um algorítimo genético evolutivo. Também está presente um algorítimo ambicioso preparado para os casos em que o algorítimo genético falha.

O algorítimo genético é um algorítimo que funciona por meio de gerações, ele cria populações e tenta aumentar o valor de *fitness* geral da geração eliminando elementos de *fitness* baixo e "procriando" elementos de *fitness* alto.

Já o algorítimo ambicioso tenta, dado uma entrada de turmas, encaixar as turmas e, quando há um conflito, cria uma nova grade. Os resultados deste algorítimo não são tão bons quando comparados com o algorítimo genético.


## 2. Algorítimo

Como citado anteriormente, o algorítimo genético possui geraçãos e populações. Além disso possui outros elementos, como seus indivíduos (ou elementos) e restrições.

Dentro do domínio do Unigrade, um indivíduo da população do algorítimo é um objeto de grade horária, que possui um cromossomo, representando as turmas que estão ativas dentre as turmas disponíveis, que são as turmas de entrada do algorítimo.

Uma adaptação que foi feita ao algorítimo genético é no momento de criar a população inicial. Ela geralmente é criada com variações aleatórias do cromossomo dos elementos, mas incluimos o resultado do algorítimo ambicioso, além dos aleatórios, na tentativa de obter melhores resultados.

A teoria por trás do algorítimo genético evolutivo é muito parecida com a teoria da evolução, em que o indivíduo mais forte tem seus genes propagados. Uma geração do algorítimo tem quatro etapas: avaliar, selecionar, cruzamento e mutação. Para cada uma destas etapas existem diversas formas de implementação, portanto descreveremos as formas utilizadas no projeto.

### Avaliar

O procesos de avaliação consiste em calcular o valor de *fitness* para cada um dos indivíduos da população. Isso acontece aplicando o elemento nas restrições (em breve entraremos em mais detalhes sobre as restrições) e calculando quantas penalidades ele obteve. Após isso, é utilizada a fórmula:

> fitness = 100 / (100 + soma_de_penalidades)

Podemos observar que o valor de *fitness* vai de 0,0 a 1,0. Quanto maior a soma das penalidades, mas próximo de 0 é o resultado.

### Selecionar

A seleção consiste em separar quais elementos devem ser mantidos e quais elementos devem ser removidos da população. A implementação escolhida é bem simples: é calculada a média de *fitness* da população atual e os elementos que possuírem *fitness* menor que 90% da média são eliminados.

### Cruzamento

O cruzamento é feito apenas entre os elementos que foram selecionados para se manter na população no passo anterior. Os elementos são escolhidos em pares aleatórios. Eles são escolhidos como os pais de dois novos indivíduos que serão adicionados a população.

É implementado o cruzamento de um ponto, em que é escolhido um ponto aleatório do cromossomo para realizar um corte e os fragmentos são recombinados.

>Exemplo de mistura:<br>
>Parente 1: A B C D E<br>
>Parente 2: F G H I J<br>
><br>
>Ponto de corte: 2<br>
><br>
>Filho 1: A B H I J<br>
>Filho 2 : F G C D E<br>

Os pais são removidos da população e os filhos são adicionados, para serem processados na próxima geração.

### Mutação

Além de todos os processos anteriores é adicionada uma chance aleatória de que uma parte do cromossomo troque de estado (ativo para inativo e vice-versa). Isso ajuda a remover vícios na população e garante que mesmo em estágios avançados de gerações do algorítimo ainda se possa ter mais variação nas grades consideradas por ele.

### Critério de parada

Quando todas as etapas são concluídas o cíclo é recomeçado até que uma das condições de parada sejam concluídas: passar do máximo de gerações, a média das 5 últimas médias de *fitness* ser maior que 0.9 (um valor alto de *fitness*) ou a população ter esvaziado. É feito um filtro para obter apenas os elementos únicos da população, eles são ordenados por *fitness* e são retornados apenas os 5 maiores, isso na tentativa de mostrar apenas os resultados mais relevantes na saída do algorítimo.

Se não houver resultados suficientes é retornado o resultado do algorítimo ambicioso como *fallback*.


## 3. Restrições

Uma restrição é responsável por julgar um elemento da população. Elas são classificadas em *Hard* e *Soft*. A diferença está na quantidade de pontos de penalidade que elas aplicam a um elemento. Considera-se que uma restrição *Hard* nunca deve acontecer na população final e uma *Soft* pode acontecer, mas não é desejada.

As seguintes restrições estão sendo utilizadas:

### Soft

#### ClassesIncludedRestrictions

Verifica se uma porcentagem de todas as turmas incluídas está ativa no cromossomo. Ou seja: se houverem 10 turmas e um mínimo de 30%, esta restrição aplicará a penalidade caso um cromossomo tenha menos que 3 turmas ativas.

#### FreeTimeRestriction

Tenta minimizar a quantidade de tempo livre entre aulas (popularmente conhecido como "janela"), evitando que a grade horária final faça com que o aluno fique ocioso entre aulas. Faz isso calculando a quantidade de horas vagas em uma semana (não são contabilizados dias que tenha menos de duas aulas). Caso a quantidade de horas vagas seja maior que a média da população então a penalidade é aplicada.

#### PriorityRestriction

Na aplicação Unigrade cada turma pode ter uma prioridade associada. Esta restrição tenta fazer com que as grades resultantes incluam turmas de maior prioridade. Ela verifica qual é o valor de prioridade total de um cromossomo e compara com uma porcentagem mínima do maior valor possível da população. Caso o valor de prioridade do cromossomo seja menor que este limiar a penalidade é aplicada.

### Hard

#### CompatibilityRestriction

Esta restrição analisa o cromossomo em busca de uma inconsistência definida pelo domínio do problema: não se pode ter duas turmas ativas que tenham horários conflitantes. A penalidade é aplicada caso uma situação dessas seja detectada.

#### NumberConsistentRestriction

Um cromossomo não pode ter todos as suas partes inativas. A penalidade é aplicada caso isso aconteça para evitar que grades horárias vazias sejam geradas.

## 4. Limitações

Durante os testes foi constatado que o algorítimo genético não trabalhava bem com menos de três turmas escohidas, por este motivo a aplicação opta por cair no algorítimo ambicioso em modo *fallback*.

Também se percebeu que existem muitos resultados repetidos, por causa da natureza aleatória do algorítimo, para combater isso foi implementado um filtro que remove duplicatas.

## 5. Referências

* SANTOS, José Luender de Lima. Uma ferramenta para geração de grades horárias utilizando algoritmos genéticos. 2016.
* PAWAR, Sunil Nilkanth; BICHKAR, Rajankumar Sadashivrao. Genetic algorithm with variable length chromosomes for network intrusion detection. International Journal of Automation and Computing, v. 12, n. 3, p. 337-342, 2015.