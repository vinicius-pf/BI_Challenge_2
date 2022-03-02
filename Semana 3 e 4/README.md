# [Semana 2](https://bit.ly/Semana2_Alura) - Alura Challenge BI

A **Alura Skimo** necessita acompanhar suas **vendas** através de um painel que comporte todas métricas necessárias. 

## Base de Dados

Para a criação dos dashboards, a empresa disponolizou um bando de dados MySQL, contendo 5 tabelas relacionadas entre si. As tabelas trazem informações complementares a respeito de clientes, produtos, pedidos e vendedores:

![image](https://user-images.githubusercontent.com/6025360/156248332-89cb66ab-eb94-42a5-bafe-2846fa55ba30.png)


- A tabela *categorias* traz informações sobre a categoria dos produtos (se é picolé ou sorvete) e conta com um ID, utilizado como chave primária.
- A tabela *clientes* traz informações sobre os clientes: Nome, endereço, gênero, data de nascimento e CPF, que funciona como um ID e chave primária da tabela.
- A tabela *itens_pedido* traz informações sobre os itens incluidos em cada pedido e suas quantidades
- A tabela *pedido* traz informações sobre os pedidos feitos: data de venda, qual foi o vendedor e qual foi o cliente. Essa tabela tem uma coluna 'ID Pedido' que funciona como chave primária.
- A tabela *produtos* traz informações sobre os produtos disponíveis para a venda como preço, custo, tamanho, sabor e família de produtos. Também conta com um ID próprio de cada produto.
- A tabela *vendedores* traz informações como data de admissão, nome, percentual de comissão e matrícula do vendedor, que funciona como chave primária.

Primeiramente o banco de dados foi recuperado no computador e depois foi feita a conexão ao Power BI. Após a importação e antes do tratamento dos dados, verifiquei as relações existentes entre as tabelas. A ferramenta já havia relacionado algumas tabelas, porém alguns relacionamentos foram criados.

### Relacionamentos

As tabelas se relacionam entre si da seguinte maneira:

Tabelas  | Coluna | Relacionamento
---------|--------|---------------
*categorias* - *pedido*|CPF - ID Cliente | 1:m
*vendedores* - *pedido* | ID vendedor | 1:m
*pedido* - *itens_pedido* | ID pedido | 1:m
*produto* - *itens_pedido* | ID Produto | 1:m
*categorias* - *produto* | ID Produto | 1:m

Essas relações foram implementadas no Power BI.

![image](https://user-images.githubusercontent.com/6025360/156248304-c9967389-2ecd-4195-a9fe-25173e20f532.png)

## Métricas

Com a base de dados, a empresa espera que algumas informações sejam exibidas no dashboard.

- Faturamento
- Ranking de produtos vendidos
- Vendedores que mais geram faturamento
- Custo
- Quantidade de vendas
- Lucro
- Categorias mais vendidas
- Ticket médio por venda

Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Dashboard de vendedores e produtos
- Dashboard de produtos: análise de cenário
- Dashboard de produtos: previsão de faturamento

Com as especificações da empresa e meu conhecimento inicial da base de dados, decidi fazer um dashboard no Power BI com 3 páginas. A primeira página funcionará como página inical trazendo algumas informações chave a respeito da empresa como custo, lucro e faturamento. Junto a essas informações, será exibido um gráfico de linhas trazendo a informação de quantidade vendida ao longo do tempo e filtros por cidade, ano e vendedor.

A segunda página terá informações dos venderores. Serão exibidos os valores de comissão, faturamento e quantidade de vendas por vendedor. Será possível escolher o vendedor por meio de filtros também. 

A última página será destinada aos produtos, com gráficos apontando as categorias e os produtos mais vendidos. Também será nessa página que será criado a análise de cenário e a previsão de faturamento.


## Tratamento de dados e criações de medidas e hierarquias

Após a recuperação do banco de dados e da importação no Power BI, analisei as informações contidas nas tabelas. Durante essa análise, percebi que a tabela *produtos* precisava ser tratada com mais calma. As outras tabelas possuíam apenas problemas pontuais, como efetuar a troca do tipo de dados, e de padronização dos nomes das colunas, deixando todos com a letra inicial em maiúscula.

### Tabela produtos

Na tabela de produtos, para poder deixar o dashboard mais dinâmico, decidi fazer alguns tratamento de dados. Esses tratamentos permitirão o uso de outros filtros, assim como criação de hierarquias dentro da tabela mais facilmente.

![image](https://user-images.githubusercontent.com/6025360/156255307-6c56f234-a39f-4fec-a75d-1bcd26e175e2.png)

Após primeira análise, decidi por dividir a coluna *Descritor* em 3 colunas distintas: *sabor*, *tamanho* e *família*. Assim poderei criar uma hierarquia de produtos começando pela família, passando por sabor e terminando em tamanho. Após isso, foram excluidos dos dados possívels caracteres brancos nos dados e a tabela foi padronizada da mesma forma que as outras.

![image](https://user-images.githubusercontent.com/6025360/156255363-47210a90-67fe-4f78-8a0a-10851fbf9a41.png)

Após esses tratamentos, comecei a criação das hierarquias. Como uma das hierarquias utiliza dados da tabela *produtos* e da tabela *categorias*, criei uma coluna na tabela produtos para receber a informação da categoria utilizando a função LOOKUPVALUE() do Power BI.

![image](https://user-images.githubusercontent.com/6025360/156255857-db4720a6-9f52-434f-aa8a-57cd8ca8d30a.png)

Durante o desenvolvimento do dashboard, percebi que existiam informações incompletas. Há informações na tabela *itens_pedido* que não estão presentes na tabela *pedidos*: os pedidos com ID '3375', '53715', '70186' e '77333' estão apenas com informações de quantidades vendidas, mas não contém informações de datas de vendas, vendedor ou cliente. Há também o pedido nº '121', que utiliza um CPF não cadastrado na base de dados e o pedido '146, que utiliza um produto não cadastrado. Essas informações estão em 20 linhas da base de dados, de um total de 213.364 linhas na tabela *itens_pedido* e em 6 linhas dentro de um total de 87.873 linhas na tabela *pedidos*. Para esse dashboard, irei excluir as linhas com as informações equivocadas e informarei a empresa a respeito dos erros.

Após a criação da tabela e limpeza dos dados, foi possível criar as hierarquias desejadas.

### Hierarquias

Foram criadas duas hierarquias para o desenvolvimento desse dashboard: **Localização** e **Produtos**. A primeira está dentro da tabela *Clientes* e a segunda na tabela *Produtos*. As hierarquias foram criadas para permitir visualizar as informações de vendas e faturamento em um único visual, halibitando a funcinalidade de *drill down*.

A hierarquia **Localização** foi criada para poder visualizar informações de estados, municípios e bairros. As informações serão trazidas em faturamento bruto, lucro e quantidade de vendas.

![image](https://user-images.githubusercontent.com/6025360/156256464-f7e524a4-9324-4cf4-bbd4-e650dc80b671.png)

A hierarquia **Produtos** foi criada para poder visualizar informações de categoria, família, sabor e tamanho. As informações serão trazidas em faturamento bruto, lucro e quantidade de vendas também.

![image](https://user-images.githubusercontent.com/6025360/156256494-2d961a0f-6fca-49ca-ba5d-d82de5a7dea9.png)

## Desenvolvimento do Dashboard

O dashboard foi desenvolvido em Power BI utlizando uma paleta de cores derivada do logo da empresa. Durante o desenvolvimento das medidas e dos visuais, decidi mudar um pouco o layout do mesmo para facilitar o entendimento. Como um bônus, também foi criada uma página para análise de cenários, estimando custos, lucro e faturamento ao modificar alguma varíavel como preço unitário ou unidade vendida.

Para a criação dos dashboards financeiro, de vendedores e de produtos, foram criadas algumas métricas para fazer o cálculo do valor. A criação de métricas permite uma legibilidade maior e fácil transferência de ideias.

![image](https://user-images.githubusercontent.com/6025360/156448445-c07d8262-db9a-4a68-b394-8db10ec8baa1.png)

Medida  | Fórumla DAX | Descrição
---------|--------|---------------
Comissão | SUMX(Vendedores,[Faturamento] * Vendedores[Comissão]) | Calcula a comissão total e por vendedor.
Custo | SUMX('Itens do Pedido', [Quantidade Vendida] * RELATED(Produtos[Custo])) | Calcula o custo de produção
Faturamento | SUMX('Itens do Pedido', [Quantidade Vendida] * RELATED(Produtos[Preço])) | Calcula o faturamento total das vendas.
Lucro | [Faturamento] - [Custo] - [Comissão] | Calcula o lucro final.
Qtd Itens Vendidos | SUM('Itens do Pedido'[Quantidade Vendida]) | Mostra a quantidade de itens vendidos.
Qtd Vendas | COUNT(Pedido[ID Pedido]) | Exibe a quantidade total de vendas no período.
Ticket Médio | DIVIDE([Faturamento], [Qtd Vendas], 0) | Calcula o ticket médio por venda.

Além das medidas anteriores, foi criadas uma nova tabela, que terá medidas para serem utilizadas na página de análise de cenários. Em conjunto com a nova tabela, foram criados parâmetros para serem ajustados pelo cliente. 


![image](https://user-images.githubusercontent.com/6025360/156449924-6c1f5ca4-ea6e-4c8b-a9cc-6f40389a59e7.png)


Todos os parâmetros foram criados da mesma forma:

![image](https://user-images.githubusercontent.com/6025360/156449800-ad858d09-d825-4efa-8a61-4c834da2ec3f.png)

Após a criação dos parâmetros, foi possível criar as novas medidas para a página de cenários.

![image](https://user-images.githubusercontent.com/6025360/156450025-b795f349-cd81-430c-ac96-d94e65a97864.png)

Medida  | Fórumla DAX | Descrição
---------|--------|---------------
Comissão prevista | *'_Medidas'[Comissão]*(1 - (((-1)*'% Comissão'[% Comissão Valor])))*  | Calcula a comissão com base nas mudanças.
Custo previsto | *'_Medidas'[Custo]*(1 - (((-1)*'% Custo'[% Custo Valor])))* | Calcula o novo custo
Faturamento Previsto | *([Ticket Previsto] * [Quantidade prevista]) * (1 + SELECTEDVALUE('% Quantidade'[% Quantidade], 0))* | Calcula o faturamento total, baseado na quantidade vendida e no preço do produto.
Lucro Previsto | [Preço Previsto] - [Custo previsto] - [Comissão prevista] | Calcula o lucro final.
Preço Previsto | *'_Medidas'[Faturamento]*(1 - (((-1)*'% Preço'[% Preço Valor])))* | Calcula o preço com base nas mudanças.
Quantidade prevista | *[Qtd Itens Vendidos] * (1 - (((-1) * '% Quantidade'[% Quantidade Valor])))*| Exibe a quantidade de itens vendidos.
Ticket Previsto | DIVIDE([Preço Previsto], [Quantidade prevista],0)) | Calcula o ticket médio por item, considerando o preço final previsto e a quantidade prevista.








