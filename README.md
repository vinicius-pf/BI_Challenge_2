# Alura Challenge BI - 2ª Edição

Neste Repositório estão os meus projetos desenvolvidos nos meses de Fevereiro e Março de 2022 como parte do [Alura Challenge BI](https://www.alura.com.br/challenges/bi-2/). O curso implementa o Challenge Based Learning, desenvolvido em partes pela Apple com o objetivo de aprofundar os conhecimentos dos alunos em uma área específica.

## Sobre

O Alura Challenge constituiu de 3 desafios semanais para que os participantes pudessem desenvolver novos conhecimentos, aprender novas ferramentas e criar um portifólio na área de Business Inteligence e ciência de dados, enquanto era simulado um fluxo de trabalho em uma empresa. 
Em cada semana do desafio foi enviado uma área de trabalho no [Trello](https://trello.com/), disponibilizando um conjunto de dados e algumas informações pertinentes da empresa, assim como informando as métricas que deveriam ser exibidas na versão final do dashboard. Além disso, foram disponibilizados links para cursos da plataforma Alura, com o intuito de aprofundar o conhecimento dos participantes.

* [Projetos desenvolvidos](#projetos-desenvolvidos)
    + [Semana 1 Mergulhando no mercado cinematográfico](#semana-1-mergulhando-no-mercado-cinematográfico)
      - [Página de Receitas](#página-de-receitas)
      - [Página de Rankings](#página-de-rankings)
      - [Página de filmes](#página-de-filmes)
    + [Semana 2 Entendendo o mercado de restaurantes da Índia.](#semana-2-entendendo-o-mercado-de-restaurantes-da-índia)
      - [Página Inicial](#página-inicial)
      - [Página de Restaurantes](#página-de-restaurantes)
    + [Semana 3 Analisando o setor de vendas da Alura Skimó.](#semana-3-analisando-o-setor-de-vendas-da-alura-skimó)


## Projetos desenvolvidos

### Semana 1 Mergulhando no mercado cinematográfico

[Clique aqui para ir ao dashboard](https://bit.ly/Semana1_Challenge)

![Página Inicial](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20inicial.PNG?raw=true)

Para essa semana, a empresa Alura Films dispinibilizou um dataset com informações sobre os 1000 filmes mais bem avaliados no [Internet Movie Database(IMDb)](https://www.imdb.com/) e requisitou algumas métricas para encontrar a combinação ideal de elenco e produção. Para o desenvolvimento do dashboard, foram requisitadas que algumas métricas estivessem presentes.

Para a criação do dashboard, criei 3 páginas com informações pertinentes a respeito de receita, notas e informações sobre os filmes para que a Alura Films consiga fazer atomada de decisão de maneira mais rápida e eficaz para suas produções. Foi criada além disso, também foi criada uma página inicial para melhorar a navegabilidade do sistema.

#### Página de Receitas

![Página Receitas](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20receita%20Atores.PNG?raw=true)

Ao abrir a página de receitas, temos as informações dos 10 atores que mais faturaram e também um gráfico com os 10 filmes com maior bilheteria. Ao lado, encontram-se 2 filtros: um de gêneros e um de classificação indicativa. Esses filtros alteram os gráficos, que passam a mostrar as informações de acordo com o filtro escolhido. Ao se clicar em alguma das barras do gráfico de atores, o gráfico de filmes também se altera, mostrando os filmes com mais receita que aquele ator participou.

Para cada gráfico, há uma dica de ferramentas.

![Dicas ator](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/Dicas%20Ator.PNG?raw=true)

Para o gráfico de atores, a dica de ferramentas trás a contagem de filmes que o ator participou, além das médias dos filmes no IMDb e também no Metacritic. Por último, uma tabela mostra os diretores com o artista mais trabalhou, em conjunto com o número de filmes da dupla.

![Dicas filmes](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/Dicas%20Filmes.PNG?raw=true)

No gráfico de filmes, a dica de ferramentas mostra o poster do filme, assim como a informação de diretor e das notas que o filme recebeu no IMDb e no Metacritic.

Nessa página há dois botões no topo. Um de 'Diretores', altera o gráfico de atores para um que ilustra os 10 diretores mais rentáveis. Esse gráfico também possui uma dica de ferramentas contendo informações de número de filmes produzido, média de notas no IMDb e no Metacritic, assim como uma tabela em que mostra quais atores mais atuaram em seus filmes, mostrando também a contagem de filmes que a dupla produziu.

![Página receita diretores](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20receita%20Diretores.PNG?raw=true)

![Dicas diretor](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/Dicas%20Diretor.PNG?raw=true)

Um outro botão faz o gráfico mostrar a receita por gênero do filme. Para este gráfico, não há dica de ferramentas. O gráfico, porém, ao selecionar uma das barras, faz a filtragem no gráfico com as receitas dos filmes.

![Página receita gêneros](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20receita%20G%C3%AAneros.PNG)

#### Página de Rankings

Ao entrar na página de rankings, 3 gráficos são mostrados: o primeiro com os 10 atores com mais filmes estrelados, o segundo com os 10 atores com a melhor média no IMDb e o terceiro com os 10 atores com melhor média no Metacritic. Essas médias são tiradas das notas dos filmes em que o ator participou. Assim como na página de receitas, encontram-filtros de gênero, classificação indicativa e ano de lançamento do filme, além da dicas de ferramenta com informações dos atores.

![Página ranking atores](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20ranking%20Atores.PNG?raw=true)

Também há 3 botões no topo da página para alterar o teor dos gráficos: um para mostrar gráficos com informações de diretores e outro com informações de filmes. O botão para as informações por diretores, apenas muda as informações de atores para diretores, também contando com as dicas de ferramentas.

![Página ranking diretores](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20ranking%20Diretores.PNG?raw=true)

Para os rankings de filmes, o primeiro gráfico passa a mostrar os filmes com mais votos no IMDb. Os outros gráficos mostram novamente as médias de cada site. Nesses gráficos as dica de ferramenta é a mesma do gráfico de filmes da primeira página.

![Página ranking filmes](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20ranking%20Filmes.PNG?raw=true)

#### Página de filmes

![Página filmes](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Filmes.PNG?raw=true)

Na última página do relatório, é exibido um resumo sobre cada filme. Com o filtro superior, é possível digitar o título do filme, o que altera as informações da página para o filme selecionado. Para cada filme, existem informações de: duração, ano de lançamento, receita, nota no IMDb, diretor, ator principal e coadjuvante, classificação indicativa, poster e uma breve sinopse do filme.


### Semana 2 Entendendo o mercado de restaurantes da Índia.

[Clique aqui para ir ao dashboard](https://bit.ly/Semana2_Challenge)


![Página Inicial](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%202/Screenshots/P%C3%A1gina%20Inicial.PNG?raw=true)

Para a segunda semana, a empresa Alura Foods entrou em contato. A empresa visa expandir o seu negócio, desejando entrar no mercado indiano. Para isso, disponibilizou uma base de dados com informações dos restaurantes do aplicativo [Zomato](https://www.zomato.com/). A empresa então requisitou que algumas informações estivessem presentes no dashboard, para que as decisões fossem tomadas com mais clareza. 

Para esse dashboard, criei 2 páginas. A primeira página traz as informações requisitadas pela empresa. A segunda também é um pedido da empresa, contendo um relatório dos restaurantes. Ambas as páginas contém 2 botões no canto esquerdo: o superior leva à página inicial, enquanto o inferior à página de relatório dos restaurantes. 

Para esse dashboard, aproveitei as cores presentes na logo da empresa: cinza e verde, e inclui as cores laranja e azul, para lembrar a bandeira indiana.

#### Página Inicial
A primeira página do dashboard, que também é a página de apresentação, mostra as informações que a empresa requisitou. Há 3 filtros de dados: um para Restaurantes, outro para cidades e um terceiro para selecionar os restaurantes que aceitam ou não reservas.

Ao lado do filtro de reservas, há 3 cartões que mostram as informações de número de restaurantes, o preço médio para duas pessoas em Rupias e a média de notas dos restaurantes no aplicativo, que varia de 0 a 5. Há dois gráficos de barras, com contagens de número de restaurantes por culinária principal e por cidades. Esses gráficos de barras são responsivos e filtram as informações das outras informações da página. Por último, há 2 gráficos de pizza, que mostram a porcentagem de restaurantes que aceitam reserva e que tem entrega online.

![Dica de ferramentas](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%202/Screenshots/Dica%20de%20ferramentas.PNG?raw=true)

Nos 4 gráficos presentes na página inicial, inclui uma dica de ferramentas que mostra o número de restaurantes, o preço médio, a nota média e uma tabela com os 5 restaurantes mais bem avaliados.

#### Página de Restaurantes

![Página de Restaurantes](https://user-images.githubusercontent.com/6025360/155611322-71f2a1ee-0ec5-44fa-8277-4da85f4eb786.png)

Apesar da empresa ter requisitado essa página, não foi especificado nenhum visual. É possível filtrar por restaurante, usando o filtro, ou por cidades, utilizando o mapa. Os filtros selecionados irão afetar os outros visuais, incluindo o título da página, que é o nome do restaurante selecionado.

Os cartões ao lado do filtro de restaurante trazem as informações sobre delivery, reserva ou entrega do restaurante. Abaixo, é possível ver as informações de preço em rúpias, em dólares, em euros e em reais. Também é possível ver a quantidade de cidades que um restaurante está presente, o número de estabelecimentos e também as informações de review dos usuários: nota média, avaliação do aplicativo e número de votos.

Por último, entre o mapa e o filtro encontram-se dois botões. O primeiro leva ao site com o menu do restaurante, o segundo para um site com as fotos do local.


### Semana 3 Analisando o setor de vendas da Alura Skimó.








