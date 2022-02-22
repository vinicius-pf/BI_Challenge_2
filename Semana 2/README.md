# [Semana 2](https://bit.ly/Semana2_Alura) - Alura Challenge BI

A **Alura Food** tem interesse em **expandir** seu negócio entrando no mercado **indiano**. Para isso, ela precisa da sua ajuda na **criação de métricas e análise dos dados** disponibilizados para tomar a **melhor decisão**.

## Base de Dados

Para isso, ela disponibilizou uma base de dados com informações de restaurantes retiradas do aplicativo Zomato, um aplicativo de busca de restaurantes para pessoas que queres sair para jantar, buscar comidas ou pedir em casa e que está presente em diversos países, como Índia, Brasil, Estados Unidos, Catar, entre outros<sup>[1](https://pt.wikipedia.org/wiki/Zomato)</sup>.

Essas informações foram entregues em 7 arquivos diferentes:

- 5 arquivos do tipo JSON, que tem as informações sobre os restaurantes
- 1 planilha do Microsoft Excel com um dicionário de código dos países
- 1 documento do Microsoft Word com descrições sobre os arquivos e suas colunas

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:

- Filtrar por cidade, restaurantes e se tem reserva
- Total de restaurantes na Índia
- Preço Médio
- Média de avaliação
- Porcentagem de restaurantes que tem ou não delivery online
- Cidades que mais possuem restaurantes
- Culinárias que mais são exploradas da Índia
- Restaurantes por cidade e suas classificações

Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Preço Médio através das moedas
- Página de estudo sobre cada restaurante

Para deixar o dashboard mais completo, também incluirei algumas métricas e etapas que acredito que possam agregar a tomada de decisão da empresa:

-
-
-


### Relacionamentos

As 5 arquivos do tipo JSON não se relacionam entre si, porém são complementares uns aos outros.

## Tratamento de dados

Primeiramente decidi tratar os dados via [Python Pandas](https://pandas.pydata.org/). Porém os arquivos JSON estão com informações aninhadas, isto é: as informações referentes ao restaurante estão em uma lista dentro de uma outra lista. Após tentar algumas soluções sem sucesso, migrei o tratamento das tabelas para a plataforma Power BI. Ao migrar para o Power BI, perdi algumas facilidades para limpeza de dados que a biblioteca Pandas permite, porém consegui resolver meu problema.

### Tratamentos no Power BI

#### Tratamento arquivos individuais
Para iniciar o tratamento, importei o arquivo 'file1.json' para a ferramenta. O arquivo entao foi lido e navegado até que as colunas do arquivo fossem mostradas.

![Primeira Etapa](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%202/Screenshots/Documenta%C3%A7%C3%A3o%20Tratamento/expandindo%20a%20coluna.PNG?raw=true)

Como primeiro problema, vi que as colunas não correspondiam com as informações que a empresa me passou. Ao estudar o arquivo, entendi que as informações requisiatadas pela empresa estavam dento da coluna *restaurants*, e que as outras podiam ser ignoradas para esse processo.

![Segunda Etapa](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%202/Screenshots/Documenta%C3%A7%C3%A3o%20Tratamento/informa%C3%A7%C3%A3o%20dos%20restaurantes.PNG?raw=true)

Por último, naveguei até que as informações desejadas dos restaurantes fossem exibidas.

![Terceira Etapa](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%202/Screenshots/Documenta%C3%A7%C3%A3o%20Tratamento/informa%C3%A7%C3%B5es%20completas.PNG?raw=true)

Esses tratamentos foram iguais para os 5 arquivos JSON. Após isso, concatenei os arquivos utilizando a funcinalidade 'Acrescentar Consultas como Novas'. Essa funcinalidade me permitiu ter uma tabela única com as informações combinadas dos 5 arquivos. Para essa tabela dei o nome de 'Restaurantes'

#### Tratamento da tabela 'Restaurantes'

Com a tabela criada, a limpeza dos dados, que seria igual nos 5 arquivos, foi unificada. Essa tabela continha mais de 29753 linhas com informações de restaurantes. Além dessas, 848 linhas estavam sem informações. Para essas linhas serem excluidas, considerei que a coluna 'restaurants.restaurant.id' como sendo não nula e também que deve ser única, o que me levou a excluir valores duplicados também nesta coluna.

Após essas tranformações, retirei de outras listas informações sobre os comentários e notas sobre o restaurante, vindos da coluna 'restaurants.restaurant.user_rating' e também sobre a localização, da coluna 'restaurants.restaurant.location'. Outras duas colunas ('restaurants.restaurant.offers' e 'restaurants.restaurant.establishment_types') também continham informações aninhadas, porém houve erro no momento de extração das informações. Por isso, exclui essas colunas.

Para terminar, a coluna com informação do tipo de culinária dos restaurantes foi dividida e algumas colunas foram renomeadas de acordo com as necessidades da empresa e do documento Word incluso.


## Desenvolvimento do Dashboard

O dashboard foi desenvolvido em Power BI. A empresa não especificou as cores desejadas, mas disponibilizou imagens de logo para serem usadas. Depois de escolhida a logo, criei o dashboard pensando em um visual escuro, utilizando a cor verde para dar destaque nos dados.

![Página Receitas](https://github.com/vinicius-pf/BI_Challenge_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20de%20receita%20Atores.PNG?raw=true)

Além da logo, também usei imagens para auxiliar o usuário. Essas imagens foram baixadas do site [Icons DB](https://www.iconsdb.com/), que disponibiliza 4215 ícones para serem utilizados em projetos pessoais ou corporativos.


  
## Ferramentas utilizadas
  Para a criação do dashboard foi utilizado o Microsoft Power BI. Para o plano de fundo foi utilizado o Microsoft Power Point. 
  
  ### Fontes dos ícones:
  
  Os ícones foram baixados do site [Icon Finder](https://www.iconfinder.com):

  [Business Collection icon set](https://www.iconfinder.com/iconsets/business-collection-2027) produzido por [phoenix icon](https://www.iconfinder.com/phoenixicon)

  [Essentials icon set](https://www.iconfinder.com/iconsets/essentials-9) produzido por [Alice Rizzo](https://www.iconfinder.com/AliceR) - Sob licensa Creative Commons (Attribution 3.0 Unported)


