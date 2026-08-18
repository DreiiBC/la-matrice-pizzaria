# La Matrice — Pizzaria Artesanal

## Sobre o projeto

Projeto de análise de vendas desenvolvido no Power BI a partir de uma base de dados de uma pizzaria artesanal.

O objetivo foi transformar os dados de pedidos e produtos em um dashboard que permitisse analisar o faturamento, a quantidade de pedidos, as pizzas vendidas e os horários de maior movimento.

A base utilizada possui aproximadamente 49 mil registros.

## Objetivos

O projeto foi desenvolvido com base nas perguntas propostas junto à base de dados, buscando responder questões como:

- Quais são os horários de maior movimento?
- Quantas pizzas são vendidas por pedido, em média?
- Quais produtos possuem maior ou menor volume de vendas?
- Quanto foi faturado ao longo do período?
- Existem períodos com maior volume de vendas?
- Existem pizzas com baixo desempenho que poderiam ser retiradas do cardápio ou utilizadas em promoções?

## Ferramentas utilizadas

- Power BI
- Power Query
- DAX
- Excel

## Dashboard

O dashboard apresenta os seguintes indicadores:

- Faturamento Total
- Quantidade de Pedidos
- Pizzas Vendidas
- Pizzas por Pedido

Principais análises:

- Evolução do Faturamento Mensal
- Faturamento por Categoria
- Volume de Pedidos por Horário
- 5 Sabores com Menor Faturamento

Também foi utilizada uma segmentação para permitir a filtragem dos dados por ano.

<img width="888" height="494" alt="dashboard" src="https://github.com/user-attachments/assets/e99611ef-ecf2-4606-9863-e2212e466896" />

## Tooltips

Foram utilizados tooltips para apresentar informações adicionais sem sobrecarregar o dashboard principal.

<img width="886" height="497" alt="tooltip-faturamento" src="https://github.com/user-attachments/assets/09b333bf-dfc6-4d2f-ac6c-1ce939878039" />

<img width="884" height="495" alt="tooltip-pedidos-hora" src="https://github.com/user-attachments/assets/cf8bada0-481c-460d-a096-b2779f0a103a" />

## Tratamento dos dados

O tratamento da base foi realizado utilizando Power Query.

Entre as principais etapas realizadas estão:

- Renomeação das colunas para facilitar a leitura dos dados;
- Ajuste dos tipos de dados;
- Tradução das categorias e tamanhos das pizzas;
- Tradução dos ingredientes e nomes dos produtos;
- Criação de dois dicionários auxiliares no Excel para realizar as traduções;
- Remoção das colunas originais após a tradução;
- Organização dos dados para utilização no Power BI.

A coluna `total_price` da base original não foi utilizada no cálculo do faturamento. O faturamento foi calculado a partir do preço unitário e da quantidade de cada item do pedido.

## Modelo de dados

O projeto foi organizado em quatro tabelas:

- `fPedido`
- `fItensPedido`
- `dProduto`
- `dCalendario`

Principais relacionamentos:

- `dCalendario` 1 → N `fPedido`
- `dProduto` 1 → N `fItensPedido`
- `fPedido` 1 → N `fItensPedido`

A separação entre pedidos e itens de pedido permite analisar tanto os pedidos realizados quanto os produtos presentes em cada pedido.

<img width="603" height="434" alt="modelo-dados" src="https://github.com/user-attachments/assets/02e36791-cb09-4913-be95-c3ef106e6a24" />

## Medidas e cálculos

Foram criadas medidas em DAX para os principais indicadores do dashboard:

- `Faturamento Total`
- `Média Pizzas por Pedido`
- `Qtd. Vendida`
- `Total Pedidos`

Também foi criada a coluna calculada `Hora Cheia`, utilizada para analisar o volume de pedidos de acordo com o horário.

Uma tabela calendário foi criada em DAX para auxiliar nas análises ao longo do tempo.

## Arquivos

- `La Matrice - Pizzaria Artesanal.pbix` — arquivo do projeto desenvolvido no Power BI.
- `Base de Dados - La Matrice.xlsx` — base utilizada no projeto.
- `Dicionário Ingredientes.xlsx` — utilizado para traduzir os ingredientes.
- `Dicionário Nomes.xlsx` — utilizado para traduzir os nomes das pizzas.

## Fonte dos dados

A base utilizada neste projeto foi disponibilizada pelo Kaggle e faz parte do conjunto de dados Pizza Place Sales, disponibilizado pelo Maven Analytics.

Kaggle: https://www.kaggle.com/datasets/nextmillionaire/pizza-sales-dataset

Maven Analytics: https://mavenanalytics.io/data-playground/pizza-place-sales

## Créditos

Os ícones utilizados no dashboard foram obtidos através do Flaticon, seguindo as condições de uso e atribuição aplicáveis aos recursos utilizados.
