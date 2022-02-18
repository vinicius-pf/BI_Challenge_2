# [Semana 1](https://bit.ly/Semana1_Challenge) - Alura Challenge BI 2ª Edição

A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de dados do IMDB com 1000 filmes. Após tratamento dos dados, a empresa espera receber um dashboard que ajudará a mesma na tomada de decisão para projetos futuros.

## Base de Dados

A empresa disponibilizou 2 tabelas no formato CSV:
  
  1. Filmes, que possui colunas com as informações de produção dos top 1000 filmes de acordo com o IMDB.
  2. Posters, que possui informações sobre o código e URL das imagens de cada filme. 

Além das tabelas, a empresa também disponibilizou um arquivo com a descrição geral de cada arquivo, assim como resumos sobre as colunas de cada tabela. Com essa descrição, alterei os títulos das colunas do arquivo 'Filmes' para o portugês durante a fase de tratamento dos dados. A coluna 'Id_Title' não foi traduzida por não haver necessidade.

Título Original da Coluna | Descrição da empresa | Título da coluna traduzido
--------------- | -------------------------------- | -------------------
Id_Title | Id do filme | Id_Title
Series_Title | Nome do filme | Título
Released_Year | Ano em que o filme foi lançado | Ano de lançamento
Certificate | Classificação obtido por esse filme | Classificação indicativa
Runtime | Tempo de execução total do filme | Duração do filme
Genre | Gênero do filme | Gênero
IMDB_Rating | Classificação do filme no site do IMDB | Nota IMDb
Overview | mini-história/resumo | Resumo
Meta_score | Pontuação obtida pelo filme | Nota Metacritic
Director | Nome do Diretor | Diretor
Star1,Star2,Star3,Star4 | Nome das Estrelas | Estrela1, Estrela2, Estrela3, Estrela4
Noofvotes | Número total de votos | Número de votos
Gross | Dinheiro ganho por esse filme | Receita

Para o outro arquivo a empresa também disponibilizou uma explicação de cada coluna, porém não houve uma tradução dos títulos de coluna

Título Original da Coluna | Descrição da empresa
--------------- | --------------------------------
Id_Title | Id do filme
Poster_Link | Link do pôster que o imdb está usando

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:

- Dinheiro ganho por Estrela 1, Estrela 2, Estrela 3 e Estrela 4
- Filmes mais votados
- Gêneros mais rentáveis
- Estrelas que mais aparecem nos filmes
- Percentual dos (n) gêneros mais explorados

Além disso, a empresa também requisitou uma exploração das colunas 'Meta_Score', 'IMDB_Rating' e 'Noofvotes'. Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Padronização classificação indicativa
- Tradução do título das colunas
- Incluir títulos em português dos filmes
- Diretores mais rentáveis
- Pares mais comuns entre diretores e estrelas

Para deixar o dashboard mais completo, também incluirei algumas métricas e etapas que acredito que possam agregar a tomada de decisão da empresa:
- Filmes com maior bilheteria
- Tradução do resumo dos filmes


### Relacionamentos

As duas tabelas se relacionam em uma cardinalidade de 1:1, por meio da coluna 'Id_Title'.


## Tratamento de dados

A tabela de Filmes precisou de um tratamento de dados após aplicação de uma análise exploratória. Para isso utilizada a linguagem [Python](https://www.python.org/), com a biblioteca [Pandas](https://pandas.pydata.org/), por meio do [Google Colab](https://colab.research.google.com/). O passo a passo da análise, incluindo comentários e referências esta no arquivo (Tratamento dos dados)[https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/dataset/Tratamento%20dos%20dados.ipynb] na pasta 'dataset'.

Com a análise exploratória, foram constatados alguns pontos de atenção. Esses foram tratados em sua maioria dentro do Python Pandas, outros foram tratados diretamente no Power BI.

Primeiro, para suprir uma das demandas extras da empresa, traduzi os títulos das colunas. Apesar de não ser necessário para as análises futuras, isso facilitará futuras aplicações do mesmo dataset.

Em seguida, dividi a coluna de generos em 3 colunas novas. A divisão se deu para que fosse possível contar corretamente a receita de cada genero individualmente. Em conjunto com a divisão, os gêneros também foram traduzidos para o português.

Para a coluna de classificação indicativa, houveram alguns problemas. Além de classificações indicativas de países diversos, incluindo Brasil, EUA e Índia, existem também classificações indicativas que não são mais utilizadas. Apesar disso, há alguns dados redundantes, que foram tratados. Como desafio extra, a empresa pediu que os dados dessa coluna fossem de unificados, trazendo apenas a classificação indicativa brasileira.

Dentro da coluna com informações das receitas, há 11 filmes com valores faltantes. Desses, 2 foram disponibilizados por serviços de streaming, sem que houvesse a venda de ingressos. Para os outros, há possibilidade de encontrar valores de receita em sites. Assim, incluirei diretamente no Power BI as informações de bilheteria para os filmes com informações de bilheteria em sites não afiliados ao IMDb. Para uma localização dos dados, também irei criar uma nova coluna com valores de bilheteria em reais. 

Há também valores faltantes na coluna referente às notas dadas pelo Metacritic. Cerca de 14% dos filmes da base de dados não possuem essa nota. Por se tratar de uma parcela considerável da base, manterei o filme sem notas. Caso seja necessário, poderei incluir uma média de acordo com o gênero principal do filme.

Durante a criação do dashboard, na fase de testes, percebi que um filme estava com a data de ano de lançamento equivocada. O filme, Apollo 13, foi lançado no ano de 1995, enquanto a base de dados constava como 1970. Essa informação foi alterada e depois os dados foram novamente importados para o Power BI

Para a tabela que contém as informações dos posters de cada filme, não houve necessidade de tratamento de dados.

### Tratamentos no Power BI

Após o tratamento de dados, importei os arquivos para a plataforma Power BI. Antes de começar a criação dos relatórios, fiz alguns tratamentos que não foram efetuados por meio do Pandas.

Primeiramente, a coluna de 'Receita' trazia as informações com divisor de milhar, o que fazia com que o Power BI não fizesse contas corretamente. Para corrigir isso, o tipo de dados foi alterado por localidade e o problema foi resolvido. Do mesmo jeito os valores de notas do IMDb e Metacritic foram alterados. De forma automática, o Power BI entendeu os valores como números, porém não considerou os pontos decimais.

Como as informações de gêneros dos filmes e estrelas estavam em colunas distintas, o Power BI não conseguia calcular de maneira rápida e eficaz quando criados filtros. Isso se tornou um problema quando a métrica de valor recebido por diretores e estrela começou a ser mostrada. Para corrigir isso, foram criadas duas tabelas auxiliares 'Gêneros' e 'Estrelas'. Para a tabela dos gêneros, importei novamente a tabela de filmes e exclui todas as colunas, mantendo apenas as colunas 'Id_Title, 'Gênero 1', 'Gênero 2' e 'Gênero 3'. Depois, tranformei as colunas relativas aos gêneros e fiz a tranposição de colunas para linhas. O mesmo tratamento foi feito para a tabela 'Estrelas'.

## Desenvolvimento do Dashboard

O dashboard foi desenvolvido em Power BI. A empresa não especificou as cores desejadas, mas disponibilizou imagens de logo para serem usadas. Depois de escolhida a logo, criei o dashboard pensando em um visual escuro, utilizando a cor verde para dar destaque nos dados.

![Página Receitas](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20receita%20Atores.PNG?raw=true)

Além da logo, também usei imagens para auxiliar o usuário. Essas imagens foram baixadas do site [Icons DB](https://www.iconsdb.com/), que disponibiliza 4215 ícones para serem utilizados em projetos pessoais ou corporativos.
