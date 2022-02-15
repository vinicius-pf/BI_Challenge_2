# [Semana 1](https://bit.ly/Semana1_Alura) - Alura Challenge BI 2ª Edição

A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de dados do IMDB com 1000 filmes. Após tratamento dos dados, a empresa espera receber um dashboard que ajudará a mesma na tomada de decisão para projetos futuros.

## Base de Dados

A empresa disponibilizou 2 tabelas no formato CSV:
  
  1. Filmes, que contém informações como: receita, ano de lançamento, resumo, título, diretor, elenco, entre outros.
  2. Posters, que contém as imagens dos posters dos filmes.

Além das tabelas, a empresa também disponibilizou um arquivo com um resumo sobre cada colunas das tabelas:


## Tratamento de dados

A tabela de Filmes precisou de um tratamento de dados após aplicação de uma análise exploratória. Para isso utilizada a linguagem [Python](https://www.python.org/), com a biblioteca [Pandas](https://pandas.pydata.org/), por meio do [Google Colab](https://colab.research.google.com/).

### Relacionamentos

As duas tabelas se relacionam em uma cardinalidade de 1:1, por meio da coluna 'Id_Title'.

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:
  

Além destas, também foram desenvolvidas algumas métricas extras:


  
## 
