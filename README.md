Projeto Análise de Dados de Livros

Este projeto realiza uma análise exploratória de dados de livros, com o objetivo de entender as tendências de publicação, a relação entre diferentes variáveis como avaliação, vendas e gênero, e o desempenho de autores e editoras.

Índice
Descrição do Projeto
Conjunto de Dados
Descrição das Colunas
Como Clonar o Repositório
Instalação das Bibliotecas
Explicação do Código
Importação de Bibliotecas
Upload do Arquivo
Carregamento dos Dados
Visualização Inicial dos Dados
Informações Detalhadas do DataFrame
Estatísticas Descritivas
Filtragem por Ano de Publicação
Verificação de Valores Ausentes
Remoção de Linhas com Nomes de Livros Ausentes
Verificação de Linhas Duplicadas
Contagem de Valores Únicos
Visualização da Distribuição de Anos de Publicação
Contagem de Livros por Gênero
Padronização da Categoria "genre fiction"
Visualização da Contagem de Livros por Gênero (Gráfico de Barras)
Avaliação Média dos Livros por Gênero
Avaliação Média dos Livros por Autor
Relação entre Gênero e Contagem de Avaliações (Boxplot)
Relação entre Gênero e Avaliação Média (Boxplot)
Relação entre Preço de Venda e Unidades Vendidas (Scatter Plot)
Contagem de Livros por Código de Linguagem
Distribuição de Livros por Linguagem (Gráfico de Pizza)
Receita Total por Editora
Contagem de Autores por Categoria de Rating
Total de Avaliações por Categoria de Rating do Autor
Relação entre Avaliação Média e Contagem de Avaliações (Scatter Plot)
Relação entre Avaliação Média e Unidades Vendidas (Scatter Plot)
Filtragem de Livros com Menos de 10000 Unidades Vendidas
Relação entre Avaliação Média e Unidades Vendidas (Filtrados) (Scatter Plot)
Receita Bruta Total por Autor
Matriz de Correlação entre Variáveis Numéricas
Relação entre Rating do Autor e Unidades Vendidas (Boxplot)
Tendência de Vendas ao Longo dos Anos (Gráfico de Linhas)
Teste de Hipóteses: Comparação de Unidades Vendidas por Rating de Autor
Glossário
Próximos Passos
Contribuição
Licença
1. Descrição do Projeto
Este projeto consiste em uma análise exploratória de um conjunto de dados de livros. O objetivo principal é obter insights sobre o mercado editorial, identificar padrões e relações entre diferentes atributos dos livros, autores e seu desempenho comercial. A análise é realizada utilizando a biblioteca Pandas para manipulação de dados, Matplotlib e Seaborn para visualização, e Scipy para testes estatísticos. O código foi desenvolvido no Google Colaboratory, facilitando a execução e compartilhamento da análise.

2. Conjunto de Dados
O conjunto de dados utilizado neste projeto é o Books_Data_Clean.csv. Ele contém informações sobre diversos livros, incluindo detalhes sobre sua publicação, autor, gênero, avaliações, vendas e outros atributos relevantes.

Descrição das Colunas
Publishing Year: Ano de publicação do livro (Numérico).
Book Name: Título do livro (Texto).
Author: Nome do autor (Texto).
language_code: Código que representa a linguagem em que o livro foi escrito (Texto).
Author_Rating: Rating do autor baseado em trabalhos prévios (Texto: 'Famous', 'Intermediate').
Book_average_rating: Rating médio dado ao livro pelos leitores (Numérico).
Book_ratings_count: Número de ratings dados pelos leitores (Numérico).
genre: Gênero do livro (Texto).
gross sales: Total de receita gerada pelas vendas do livro (Numérico).
publisher revenue: A receita recebida pela publicadora do livro (Numérico).
sale price: Preço de venda do livro (Numérico).
sales rank: Ranking da venda do livro (Numérico).
units sold: Número de unidades vendidas do livro (Numérico).
3. Como Clonar o Repositório
Para obter uma cópia local deste projeto, você pode clonar o repositório do GitHub utilizando o seguinte comando no seu terminal:

git clone [URL_DO_SEU_REPOSITÓRIO]

Certifique-se de substituir URL_DO_SEU_REPOSITÓRIO pelo link real do seu repositório no GitHub.

4. Instalação das Bibliotecas
As bibliotecas necessárias para executar este projeto são:

pandas: Para manipulação e análise de dados tabulares.
matplotlib: Para criação de gráficos e visualizações básicas.
seaborn: Para criação de gráficos estatísticos mais avançados.
scipy: Para realizar testes estatísticos.
google-colab: Para funcionalidades específicas do Google Colaboratory (como o upload de arquivos).
Você pode instalar todas essas bibliotecas utilizando o pip, o gerenciador de pacotes do Python. Execute o seguinte comando no seu terminal:

pip install pandas matplotlib seaborn scipy google-colab

Se você estiver utilizando um ambiente virtual (recomendado), certifique-se de que o ambiente esteja ativado antes de executar o comando.

5. Explicação do Código
O código presente no notebook do Google Colab é dividido em blocos lógicos, cada um responsável por uma etapa da análise. Abaixo, uma explicação detalhada de cada bloco:

Importação de Bibliotecas
Este bloco importa as bibliotecas necessárias para o projeto.

import pandas as pd

Importa a biblioteca Pandas e a atribui ao alias pd. Pandas é fundamental para trabalhar com DataFrames, que são estruturas de dados tabulares.

import matplotlib.pyplot as plt

Importa o módulo pyplot da biblioteca Matplotlib e o atribui ao alias plt. Matplotlib é utilizada para criar gráficos e visualizações.

import seaborn as sns

Importa a biblioteca Seaborn e a atribui ao alias sns. Seaborn é construída sobre o Matplotlib e oferece uma interface de alto nível para criar gráficos estatísticos informativos e atraentes.

from google.colab import files

Importa o módulo files da biblioteca google.colab. Este módulo fornece funcionalidades para interagir com o sistema de arquivos do ambiente Colab, como fazer upload de arquivos.

Upload do Arquivo
Este bloco permite que o usuário faça o upload do arquivo de dados diretamente no ambiente do Google Colab.

uploaded = files.upload()

Chama a função upload() do módulo files. Ao executar esta linha, uma interface gráfica será exibida para que o usuário possa selecionar e fazer o upload do arquivo Books_Data_Clean.csv. A variável uploaded armazenará informações sobre os arquivos carregados.

Carregamento dos Dados
Este bloco carrega o arquivo CSV para um DataFrame do Pandas.

df = pd.read_csv('Books_Data_Clean.csv')

Utiliza a função read_csv() do Pandas para ler o conteúdo do arquivo Books_Data_Clean.csv e armazená-lo em um DataFrame chamado df. Um DataFrame é uma estrutura de dados bidimensional, semelhante a uma tabela.

Visualização Inicial dos Dados
Este bloco exibe as primeiras linhas do DataFrame para uma inspeção inicial dos dados.

df.head(5)

A função head(5) exibe as 5 primeiras linhas do DataFrame df, permitindo visualizar as colunas e alguns exemplos de dados. O número dentro dos parênteses pode ser alterado para mostrar mais ou menos linhas.

Informações Detalhadas do DataFrame
Este bloco fornece um resumo das informações do DataFrame, como o número de linhas, colunas, tipos de dados e a quantidade de valores não nulos em cada coluna.

df.info()

A função info() retorna um resumo conciso do DataFrame df, útil para entender a estrutura e a integridade dos dados.

Estatísticas Descritivas
Este bloco calcula e exibe estatísticas descritivas das colunas numéricas do DataFrame, como média, desvio padrão, mínimo, máximo e percentis.

df.describe()

A função describe() calcula e exibe um resumo estatístico das colunas numéricas em df. Isso ajuda a ter uma visão geral da distribuição dos dados numéricos.

Filtragem por Ano de Publicação
Este bloco filtra o DataFrame para incluir apenas livros publicados a partir do ano 1900.

df = df[(df["Publishing Year"] >= 1900)]

Cria um novo DataFrame df contendo apenas as linhas onde o valor da coluna "Publishing Year" é maior ou igual a 1900. Isso é útil para focar em publicações mais recentes.

Verificação de Valores Ausentes
Este bloco verifica a quantidade de valores ausentes (NaN) em cada coluna do DataFrame.

df.isna().sum()

df.isna() retorna um DataFrame booleano onde True indica um valor ausente e False indica um valor presente. A função sum() então soma os valores True (que são interpretados como 1) por coluna, fornecendo o número total de valores ausentes em cada uma.

Remoção de Linhas com Nomes de Livros Ausentes
Este bloco remove as linhas onde o nome do livro (coluna "Book Name") está ausente.

df = df[(~df["Book Name"].isna())]

df["Book Name"].isna() retorna uma Series booleana indicando onde os valores na coluna "Book Name" são ausentes. O operador ~ inverte essa Series, de forma que True indica valores não ausentes. A linha de código então cria um novo DataFrame df contendo apenas as linhas onde o nome do livro não é nulo.

Verificação de Linhas Duplicadas
Este bloco verifica se existem linhas duplicadas no DataFrame.

df.duplicated()

A função duplicated() retorna uma Series booleana onde True indica uma linha que é duplicada em relação a uma linha anterior, e False indica o contrário.

df.duplicated().sum()

Similar ao tratamento de valores ausentes, .sum() aqui conta o número total de linhas duplicadas (onde o resultado de duplicated() é True).

Contagem de Valores Únicos
Este bloco conta o número de valores únicos em cada coluna do DataFrame.

df.nunique()

A função nunique() retorna uma Series contendo o número de valores únicos em cada coluna do DataFrame df. Isso ajuda a entender a diversidade dos dados em cada atributo.

Visualização da Distribuição de Anos de Publicação
Este bloco cria um histograma para visualizar a distribuição dos anos de publicação dos livros.

plt.hist(df["Publishing Year"])

Utiliza a função hist() do Matplotlib para criar um histograma da coluna "Publishing Year". O histograma mostra a frequência de livros publicados em diferentes intervalos de anos.

plt.xlabel("Publishing Year")

Define o rótulo do eixo x do gráfico como "Publishing Year".

plt.ylabel("Frequency")

Define o rótulo do eixo y do gráfico como "Frequency" (frequência).

plt.title("Distribution of Publishing Years")

Define o título do gráfico como "Distribution of Publishing Years".

plt.show()

Exibe o gráfico criado.

Contagem de Livros por Gênero
Este bloco conta o número de livros em cada gênero.

df["genre"].value_counts()

A função value_counts() retorna uma Series contendo a contagem de ocorrências de cada valor único na coluna "genre". Isso mostra quantos livros pertencem a cada gênero.

Padronização da Categoria "genre fiction"
Este bloco padroniza a categoria "genre fiction" para apenas "fiction".

df["genre"] = df["genre"].apply(lambda genre: "fiction" if genre == "genre fiction" else genre)

A função apply() aplica uma função a cada elemento da coluna "genre". A função lambda verifica se o gênero é "genre fiction" e, se for, o substitui por "fiction"; caso contrário, mantém o gênero original.

df["genre"].value_counts()

Exibe novamente a contagem de livros por gênero após a padronização.

Visualização da Contagem de Livros por Gênero (Gráfico de Barras)
Este bloco cria um gráfico de barras para visualizar a contagem de livros por gênero.

df["genre"].value_counts().plot(kind="bar")

Utiliza a função plot() com o argumento kind="bar" para criar um gráfico de barras a partir da Series de contagem de gêneros. O eixo x representa os gêneros e o eixo y representa a contagem de livros em cada gênero.

Avaliação Média dos Livros por Gênero
Este bloco calcula a avaliação média dos livros para cada gênero e os exibe em ordem decrescente de avaliação.

df.groupby("genre")["Book_average_rating"].mean().sort_values(ascending=False)

A função groupby("genre") agrupa o DataFrame pelas categorias únicas na coluna "genre". Em seguida, ["Book_average_rating"].mean() calcula a média da coluna "Book_average_rating" para cada grupo (gênero). Finalmente, sort_values(ascending=False) ordena os resultados em ordem decrescente da avaliação média.

Avaliação Média dos Livros por Autor
Este bloco calcula a avaliação média dos livros para cada autor e os exibe em ordem decrescente de avaliação.

df.groupby("Author")["Book_average_rating"].mean().sort_values(ascending=False)

Similar ao bloco anterior, este agrupa o DataFrame pela coluna "Author" e calcula a média da coluna "Book_average_rating" para cada autor, ordenando os resultados pela avaliação média em ordem decrescente.

Relação entre Gênero e Contagem de Avaliações (Boxplot)
Este bloco cria um boxplot para visualizar a distribuição da contagem de avaliações para cada gênero.

sns.boxplot(x="genre", y="Book_ratings_count", data=df)

Utiliza a função boxplot() do Seaborn para criar um gráfico de caixa. O eixo x representa os gêneros, o eixo y representa a contagem de avaliações, e data=df especifica o DataFrame a ser utilizado. O boxplot mostra a mediana, os quartis e os outliers da contagem de avaliações para cada gênero.

plt.xlabel("Genero")

Define o rótulo do eixo x como "Genero".

Relação entre Gênero e Avaliação Média (Boxplot)
Este bloco cria um boxplot para visualizar a distribuição da avaliação média para cada gênero.

sns.boxplot(x="genre", y="Book_average_rating", data=df)

Similar ao bloco anterior, este cria um boxplot com os gêneros no eixo x e a avaliação média no eixo y, mostrando a distribuição das avaliações médias por gênero.

plt.xlabel("Genero")

Define o rótulo do eixo x como "Genero".

Relação entre Preço de Venda e Unidades Vendidas (Scatter Plot)
Este bloco cria um gráfico de dispersão para visualizar a relação entre o preço de venda e o número de unidades vendidas dos livros.

plt.scatter(df["sale price"], df["units sold"])

Utiliza a função scatter() do Matplotlib para criar um gráfico de dispersão. Cada ponto no gráfico representa um livro, com a posição no eixo x determinada pelo preço de venda e a posição no eixo y pelo número de unidades vendidas.

plt.xlabel("Sale_price")

Define o rótulo do eixo x como "Sale_price" (preço de venda).

plt.ylabel("Units sold")

Define o rótulo do eixo y como "Units sold" (unidades vendidas).

Contagem de Livros por Código de Linguagem
Este bloco conta o número de livros em cada código de linguagem.

df["language_code"].value_counts()

Similar à contagem por gênero, esta função retorna a contagem de ocorrências de cada código de linguagem na coluna "language_code".

language_counts = df["language_code"].value_counts()

Armazena a Series resultante da contagem de códigos de linguagem na variável language_counts.

Distribuição de Livros por Linguagem (Gráfico de Pizza)
Este bloco cria um gráfico de pizza para visualizar a distribuição dos livros por linguagem.

plt.pie(language_counts, labels=language_counts.index)

Utiliza a função pie() do Matplotlib para criar um gráfico de pizza. language_counts fornece os tamanhos das fatias (proporcional à contagem de cada linguagem), e labels=language_counts.index define os rótulos de cada fatia com os códigos de linguagem.

Receita Total por Editora
Este bloco calcula a receita total gerada por cada editora e a exibe em ordem decrescente.

df.groupby("Publisher ")["publisher revenue"].sum().sort_values(ascending=False)

Agrupa o DataFrame pela coluna "Publisher " (note o espaço no nome) e calcula a soma da coluna "publisher revenue" para cada editora, ordenando os resultados pela receita total em ordem decrescente.

Contagem de Autores por Categoria de Rating
Este bloco conta o número de autores em cada categoria de rating ("Famous", "Intermediate").

df["Author_Rating"].value_counts()

Retorna a contagem de ocorrências de cada categoria única na coluna "Author_Rating".

Total de Avaliações por Categoria de Rating do Autor
Este bloco calcula o número total de avaliações de livros para cada categoria de rating do autor.

df.groupby("Author_Rating")["Book_ratings_count"].sum()

Agrupa o DataFrame pela coluna "Author_Rating" e calcula a soma da coluna "Book_ratings_count" para cada grupo.

Relação entre Avaliação Média e Contagem de Avaliações (Scatter Plot)
Este bloco cria um gráfico de dispersão para visualizar a relação entre a avaliação média dos livros e o número de avaliações que receberam.

plt.scatter(df["Book_average_rating"], df["Book_ratings_count"])

Cria um scatter plot com a avaliação média no eixo x e a contagem de avaliações no eixo y.

Relação entre Avaliação Média e Unidades Vendidas (Scatter Plot)
Este bloco cria um gráfico de dispersão para visualizar a relação entre a avaliação média dos livros e o número de unidades vendidas.

plt.scatter(df["Book_average_rating"], df["units sold"])

Cria um scatter plot com a avaliação média no eixo x e as unidades vendidas no eixo y.

Filtragem de Livros com Menos de 10000 Unidades Vendidas
Este bloco cria uma máscara booleana para identificar livros com menos de 10000 unidades vendidas.

booleano = df["units sold"] < 10000

Cria uma Series booleana chamada booleano onde True indica que o número de unidades vendidas é menor que 10000, e False caso contrário.

Relação entre Avaliação Média e Unidades Vendidas (Filtrados) (Scatter Plot)
Este bloco cria um gráfico de dispersão para visualizar a relação entre a avaliação média e as unidades vendidas, apenas para os livros com menos de 10000 unidades vendidas.

plt.scatter(df[(booleano)]["Book_average_rating"], df[(booleano)]["units sold"])

Utiliza a máscara booleana booleano para selecionar apenas as linhas do DataFrame onde a condição é True, e então cria um scatter plot da avaliação média contra as unidades vendidas para esses livros filtrados.

Receita Bruta Total por Autor
Este bloco calcula a receita bruta total gerada por cada autor e a exibe em ordem decrescente.

df.groupby("Author")["gross sales"].sum().sort_values(ascending=False)

Agrupa o DataFrame pela coluna "Author" e calcula a soma da coluna "gross sales" para cada autor, ordenando os resultados pela receita bruta total em ordem decrescente.

Matriz de Correlação entre Variáveis Numéricas
Este bloco calcula a matriz de correlação entre algumas colunas numéricas do DataFrame.

df[["Book_average_rating", "Book_ratings_count", "gross sales", "sale price"]].corr()

Seleciona as colunas "Book_average_rating", "Book_ratings_count", "gross sales" e "sale price" do DataFrame e utiliza a função corr() para calcular a matriz de correlação entre elas. A matriz mostra os coeficientes de correlação de Pearson, que medem a força e a direção da relação linear entre cada par de variáveis.

Relação entre Rating do Autor e Unidades Vendidas (Boxplot)
Este bloco cria um boxplot para visualizar a distribuição das unidades vendidas para cada categoria de rating do autor.

sns.boxplot(x="Author_Rating", y="units sold", data=df)

Cria um boxplot com as categorias de rating do autor no eixo x e o número de unidades vendidas no eixo y, mostrando a distribuição das vendas para autores "Famous" e "Intermediate".

Tendência de Vendas ao Longo dos Anos (Gráfico de Linhas)
Este bloco calcula o total de unidades vendidas por ano de publicação e cria um gráfico de linhas para visualizar a tendência ao longo do tempo.

df.groupby("Publishing Year")["units sold"].sum().plot(kind="line", marker="o")

Agrupa o DataFrame pelo "Publishing Year", calcula a soma das "units sold" para cada ano e utiliza a função plot(kind="line", marker="o") para criar um gráfico de linhas com marcadores nos pontos de dados, mostrando a evolução do total de unidades vendidas ao longo dos anos.

Teste de Hipóteses: Comparação de Unidades Vendidas por Rating de Autor
Este bloco realiza um teste t de Student para comparar as médias de unidades vendidas entre autores com rating "Famous" e "Intermediate".

import scipy.stats as stats

Garante que o módulo stats da biblioteca Scipy esteja importado.

grupo_A = df[(df['Author_Rating'] == 'Famous')]['units sold']

Cria uma Series contendo as unidades vendidas dos livros de autores com "Author_Rating" igual a 'Famous'.

grupo_B = df[(df['Author_Rating'] == 'Intermediate')]['units sold']

Cria uma Series contendo as unidades vendidas dos livros de autores com "Author_Rating" igual a 'Intermediate'.

t_stat, p_val = stats.ttest_ind(grupo_A, grupo_B, equal_var=False)

Utiliza a função ttest_ind() para realizar um teste t de Student para amostras independentes entre os dois grupos de unidades vendidas. O argumento equal_var=False indica que não estamos assumindo que as variâncias dos dois grupos são iguais (teste de Welch). A função retorna a estatística t (t_stat) e o valor p (p_val).

print("Estatística t:", t_stat)

Imprime o valor da estatística t calculada.

print("Valor p:", p_val)

Imprime o valor p do teste. O valor p indica a probabilidade de observar os dados (ou dados mais extremos) se não houver diferença real entre as médias dos dois grupos. Um valor p baixo (geralmente abaixo de 0.05) sugere que há uma diferença estatisticamente significativa.

6. Glossário
DataFrame: Uma estrutura de dados tabular bidimensional fornecida pela biblioteca Pandas, semelhante a uma planilha ou tabela de banco de dados.
Histograma: Um tipo de gráfico que representa a distribuição de frequências de um conjunto de dados em intervalos específicos.
Gráfico de Barras: Um gráfico que utiliza barras retangulares com comprimentos proporcionais aos valores que representam.
Boxplot (Diagrama de Caixa): Um gráfico que resume a distribuição de um conjunto de dados com base em cinco números: mínimo, primeiro quartil (Q1), mediana (Q2), terceiro quartil (Q3) e máximo. Também pode identificar outliers.
Scatter Plot (Gráfico de Dispersão): Um tipo de gráfico que utiliza pontos para representar os valores de duas variáveis diferentes, permitindo observar a relação entre elas.
Gráfico de Pizza: Um gráfico circular dividido em fatias proporcionais aos valores que representam.
Matriz de Correlação: Uma tabela que mostra os coeficientes de correlação entre pares de variáveis em um conjunto de dados.
Teste t de Student: Um teste estatístico utilizado para determinar se há uma diferença significativa entre as médias de dois grupos. O teste para amostras independentes é usado quando os dois grupos são independentes um do outro.
Valor p (p-value): A probabilidade de obter resultados tão extremos (ou mais extremos) quanto os observados, assumindo que a hipótese nula é verdadeira. Um valor p baixo geralmente indica evidência contra a hipótese nula.
Variância: Uma medida de dispersão estatística que indica o quão espalhados estão os valores de um conjunto de dados em relação à sua média.
7. Próximos Passos
Este projeto fornece uma análise exploratória inicial dos dados de livros. Alguns próximos passos interessantes poderiam incluir:

Análise de séries temporais mais aprofundada: Investigar tendências de vendas e publicações ao longo do tempo com modelos mais sofisticados.
Modelagem preditiva: Construir modelos para prever a avaliação de um livro ou suas vendas com base em seus atributos.
Análise de sentimento nos títulos e resumos: Se dados de texto adicionais estiverem disponíveis, realizar análise de sentimento para entender a percepção dos livros.
Comparação com outros conjuntos de dados: Integrar e comparar esses dados com informações de outras fontes para obter insights mais amplos sobre o mercado editorial.
Desenvolvimento de um dashboard interativo: Criar um painel interativo utilizando ferramentas como Plotly Dash ou Streamlit para facilitar a exploração dos dados.
8. Contribuição
Contribuições para este projeto são bem-vindas! Se você tiver sugestões de melhorias, novas análises ou correções de bugs, sinta-se à vontade para abrir uma issue ou enviar um pull request.

