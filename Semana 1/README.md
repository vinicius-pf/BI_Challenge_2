# [Semana 1](https://bit.ly/Semana1_Alura) - Alura Challenge BI 2ª Edição

A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de dados do IMDB com 1000 filmes. Após tratamento dos dados, a empresa espera receber um dashboard que ajudará a mesma na tomada de decisão para projetos futuros.

## Base de Dados

A empresa disponibilizou 2 tabelas no formato CSV, com informações de textos e dados em inglês.:
  
  1. Filmes, que contém informações como: receita, ano de lançamento, resumo, título, diretor, elenco, entre outros.
  2. Posters, que contém as imagens dos posters dos filmes.

Além das tabelas, a empresa também disponibilizou um arquivo com um resumo sobre cada colunas das tabelas. Com essa descrição, alterei os títulos das colunas para o portugês durante a fase de tratamento dos dados.

Título Original da Coluna | Descrição da empresa | Título traduzido
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



## Tratamento de dados

A tabela de Filmes precisou de um tratamento de dados após aplicação de uma análise exploratória. Para isso utilizada a linguagem [Python](https://www.python.org/), com a biblioteca [Pandas](https://pandas.pydata.org/), por meio do [Google Colab](https://colab.research.google.com/).

### Relacionamentos

As duas tabelas se relacionam em uma cardinalidade de 1:1, por meio da coluna 'Id_Title'.

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:
  

Além destas, também foram desenvolvidas algumas métricas extras:


  
## 
