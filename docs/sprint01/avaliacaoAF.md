# Avaliação do Protótipo de Alta Fidelidade

## Objetivo da Avaliação

A avaliação tem por objetivo identificar problemas na interação e na interface que prejudiquem a qualidade de uso do sistema. Buscando entender como o usuário se comporta em contato com a ferramenta de forma a identificar possíveis falhas no design que afetem o usuário, o impedindo ou atrapalhando a experiência com o sistema. 

## Escopo da Avaliação

A avaliação se dará por observação do uso do protótipo de forma que seja possível identificar os possíveis erros de design. Os passos que deverão ser realizados são em boa parte parecidos com os passos que um usuário real eria na aplicação, com os devidos ajustes.

- Acessar lista de produtos sem ter de realizar o login
- Realizar login na plataforma
- Identificar do que se trata o anúncio
- Realizar uma compra pelo site

## Metodologia da Avaliação

Coletar dados através da observação em laboratório do usuário ao tentar realizar as tarefas solicitadas. De forma que possam ser coletados dados para a análise posterior da interface.  

## GQM
GQM é uma ferramenta utilizada para um sistema de metrificação direcionado por objetivos e possui normalmente 6 passos. É bastante utilizado na Engenharia de Software para planejar medições.

<ul>
<li><strong>Goal 1: Analisar a experiência do usuário, de forma que ele não esteja logado na plataforma;</strong></li>
</ul>
<ul>
<li>Questions
<ul>
<li><strong>Quantos passos o usuário deve realizar, até atingir o seu objetivo final?</strong></li>
<li><strong>Qual é o grau de satisfação do usuário após a utilização do protótipo, em comparação ao site?</strong></li>
</ul>
</li>
</ul>
<ul>
<li>Metrics
<ul>
<li><strong>Métrica 1: Cliques no Site para consultar o valor de um item</strong></li>
<li>Questão: a);</li>
<li>Tipo: Direta;</li>
<li>Mensura: QtdCliques <= 6 (*QtdCliques → Quantidade de Cliques);</li>
<li>Forma de coleta: A partir da análise do teste de usabilidade do protótipo que indica a quantidade de cliques até atingir o objetivo final;</li>
<li>Escala de medição: Nominal</li>
<li>Indicador:</li>
<li>Jornada ruim:  QtdCliques > 6;</li>
<li>Jornada satisfatória:  QtdCliques = 6;</li>
<li>Jornada excelente: QtdCliques < 6;</li>
</ul>
<ul>
<li><strong>Métrica 2: Tempo na utilização do site</strong></li>
<li>Questões: a) b)</li>
<li>Tipo: Direta;</li>
<li>Mensura: Análise do tempo de utilização do site TP <= TS (TP = Tempo de utilização do Protótipo, TS = Tempo de utilização do Site);</li>
<li>Forma de coleta: A partir da análise do teste de usabilidade do protótipo e do site que indica o tempo de utilização da plataforma;</li>
<li>Escala de medição: Nominal;</li>
<li>Indicador:</li>
<li>Protótipo falho: TP > TS;</li>
<li>Protótipo satisfatório: TP = TS;</li>
<li>Protótipo bem implementada: TP < TS;</li>
</ul>
<ul>
<li><strong>Métrica 3: Nível de satisfação do usuário após o uso do protótipo</strong></li>
<li>Questão: b);</li>
<li>Tipo: Indireta;</li>
<li>Mensura: Coleta da satisfação com a metodologia de NPS (Net Promoter Score);</li>
<li>Forma de coleta: Manualmente, após o usuário utilizar o protótipo;</li>
<li>Escala de medição: Racional;</li>
<li>Indicador:</li>
<li>Usuário Promotor: 9 <= NPS <=10;</li>
<li>Usuário Neutro: 7 <= NPS <= 8;</li>
<li>Usuário Detrator: NPS <= 6;</li>
</ul>
</ul>
