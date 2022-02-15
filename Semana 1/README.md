# [Semana 1](https://bit.ly/Semana1_Alura) - Alura Challenge BI 2ª Edição

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


### Relacionamentos

As duas tabelas se relacionam em uma cardinalidade de 1:1, por meio da coluna 'Id_Title'.

## Tratamento de dados

A tabela de Filmes precisou de um tratamento de dados após aplicação de uma análise exploratória. Para isso utilizada a linguagem [Python](https://www.python.org/), com a biblioteca [Pandas](https://pandas.pydata.org/), por meio do [Google Colab](https://colab.research.google.com/).


### Transformações no power Bi

receita de texto para número decimal fixo

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:
  

Além destas, também foram desenvolvidas algumas métricas extras:


  
## 
