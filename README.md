Dataset Para Modelagem de Dados

#Aplicação do conhecimento de limpeza e organização de dados (data cleaning & data wrangling) para estruturar uma base de dados para modelagem. Estudo de Caso: Uma empresa do ramo de e-commerce contratou você para levantar os indicadores de recência, frequência e ticket médio (RFM) dos seus clientes. A saber RFM: 
•	R (Recency): Tempo que o cliente realizou a última compra (em dias) 
•	F (Frequency): Quantidade de compras realizadas pelo cliente 
•	M (Monetary): Valor do ticket médio gasto pelo cliente onde ticket médio = média do total gasto por pedido para cada cliente. 
Para isso, recebemos uma base de dados (arquivo csv) e construímos um código em Python que gera um output também csv, porém contendo apenas a identificação do cliente e métricas RFM. Com base no contexto acima e metas do negócio determinantes, podemos avaliar as seguintes considerações:

1.	Leitura do arquivo e inspecione os dados: 
Pesquisar o mercado apontando os produtos que já existem hoje e seus diferenciais. É importante apresentar de forma clara os concorrentes diretos e indiretos, e destacar seus diferenciais e pontos fortes.
1.1. Lendo o dataset
1.2. Utilizando o describe para verificar a distribuição dos dados
1.3. Analisando o tipo dos dados

2.	Valores faltantes na identificação do cliente: 
2.1. Verificando os valores nulos com o isna e utilize a função sum para a somar a quantidade de nulos
2.2. Utilizando a função dropna para remover os nulos

3.	Preços unitários e quantidade de produtos iguais ou inferior a 0: 
3.1. Realizando um filtro para verificar se existem dados nulos ou menor que zero na coluna de preços
3.2. Filtrando o dataset apenas para conter preços acima de zero
3.3. Realizando um filtro para verificar se existem dados nulos ou menor que zero na coluna de quantidade
3.4. Filtrando o dataset apenas para conter quantidade acima de zero

4.	Verifique se existem linhas duplicadas: 
4.1. Verificando se tem linhas duplicadas com a função duplicated
4.2. Drope as linhas duplicadas

5.	Tipos de dados da coluna: 
5.1. Corrigindo o tipo de dado do CustomerID
5.2. Corrigindo o tipo de dado da InvoiceDate

6.	Tratando os outliers: 
Removendo os outliers extremos em que a quantidade do item na compra é superior a 10.000, e o preço unitário é maior que 5.000.

7.	Criando uma coluna adicional: 
Utilizando as colunas Quantidade do Produto e Preço Initário do Produto criamos uma coluna adicional com o Preço Total da Compra.

8.	Última data: 
Utilizando a função max(). Calculamos a data da última compra no dataset como um todo, pois utilizamos este valor como data de comparação para cálculo da recência.

9.	Plotando gráficos: 
9.1. Top 10 países com maior valor em vendas
9.2. Top 10 produtos mais vendidos
9.3. Valor de venda total por mês
9.4. Valor de venda total por mês e por país (considere apenas os top 10) 

10.	Cálculo do RFM: 
Agrupando os dados por cliente e pedido/compra (InvoiceNo) e obtemos a data e o preço total do pedido. Com isso, calculamos o RFM, onde:
- R é a recência, diferença em dias da última compra do cliente e da última compra disponível no conjunto de dados, que calcularam previamente.
- F é a frequência, ou seja, a quantidade de compras feitas pelo cliente.
- M é o ticket médio, ou seja, a média das compras feitas pelo cliente.
