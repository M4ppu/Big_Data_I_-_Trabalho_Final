# DS-PY-015 Big Data I - Trabalho Final

## Introdução
Este repositório foi criado com o objetivo de hospedar os arquivos relativos ao trabalho final do módulo "Big Data I" da Turma #942 do curso Santander Coders da escola Ada Tech.

## O Grupo:
- Daniel Rocha (danielsantos852@gmail.com)
- Edgar Yamagata (edgar.yamagata@gmail.com)
- Guilherme Ribeiro (guilherme_f_ribeiro@hotmail.com)
- Sabrina zani (sabrinazani2000@gmail.com)
- Luiza Lima (luiza-97@hotmail.com)

## O trabalho
No presente trabalho, serão aplicadas as técnicas aprendidas em aula para a criação de um processo de ETL (Extraction, Transform, and Load) na plataforma de cloud Databricks Community (https://community.cloud.databricks.com/).

### Objetivo Geral
- Construir uma pipeline de ETL (Extract, Transform, and Load) para a construção de um Data Warehouse na plataforma Databricks Community.

### Objetivos Específicos
1. Pesquisar e escolher um dataset para utilização no trabalho;

2. Importar as tabelas do dataset, como dataframes, para um Notebook no Databricks Community;

3. Criar uma camada "raw" com os dataframes importados salvos em formato parquet;

4. Realizar a limpeza dos datasets (títulos das colunas, dados e tipos de dados);

5. Criar uma camada "refined" com os dataframes limpos salvos em formato parquet;

6. Gerar, a partir dos dataframes limpos, novos dataframes com KPIs (Key Performance 
Indicators) de interesse;

7. Modelar a base em formato Star Schema ou Snowflake para a criação do Data Warehouse;

8. Criar uma camada "trusted" com todos os dataframes da base salvos em formato parquet;

9. Criar um diagrama representativo da estrura de diretórios do projeto utilizando a ferramenta Diagrams (https://www.diagrams.net/);

10. Disponibilizar todo o projeto em um repositório no GitHub (https://github.com/).

### Dataset utilizado

#### 1. Top 1000 Youtube channels
> fonte: https://us.youtubers.me/global/all/top-1000-youtube-channels

Apresenta um Top 1000 de canais do Youtube com maior número de visualizações de videos.

##### 1.1. Tabela de dados
Dimensões: 1000 linhas x 7 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers: Quantidade de inscritos no canal;
- Video Views: Somatório de todas as visualizações dos videos do canal;
- Video Count: Quantidade de videos carregados no canal;
- Category: Categoria do conteúdo do canal;
- Started: Ano de criação do canal no Youtube.

##### 1.2. Tabela de métricas
Dimensões: 1000 linhas x 5 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers/Year: Quantidade média de inscritos por ano no canal;
- Video Views/Year: Quantidade média de visualizações dos videos por ano no canal;
- Video Count/Year: Quantidade média de videos carregados no canal por ano;

#### 2. Top 1000 Youtube videos
> fonte: https://us.youtubers.me/global/all/top-1000-youtube-videos

Apresenta um Top 1000 de videos do Youtube com maior número de visualizações.

##### 2.1. Tabela de dados
Dimensões: 1000 linhas x 7 colunas

Colunas:
- Rank: Posição do video no Top 1000;
- Video: Nome do video;
- Video Views: Quantidade de visualizações do video;
- Likes: Quantidade de likes do video;
- Dislikes: Quantidade de dislikes do video;
- Category: Categoria do conteúdo do video;
- Published: Ano em que o video foi publicado no Youtube.

##### 2.2. Tabela de métricas
Dimensões: 1000 linhas x 5 colunas

Colunas:
- Rank: Posição do video no Top 1000;
- Video: Nome do video;
- Video Views/Year: Quantidade média de visualizações do video por ano;
- Likes/Year: Quantidade média de likes do video por ano;
- Dislikes/Year: Quantidade média de dislikes do video por ano.

#### 3. Most subscribed 1000 Youtube channels
> fonte: https://us.youtubers.me/global/all/top-1000-most-subscribed-youtube-channels

Apresenta um Top 1000 de canais do Youtube com maior número de inscritos.

##### 3.1. Tabela de dados
Dimensões: 1000 linhas x 7 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers: Quantidade de inscritos no canal;
- Video Views: Somatório de todas as visualizações dos videos do canal;
- Video Count: Quantidade de videos carregados no canal;
- Category: Categoria do conteúdo do canal;
- Started: Ano de criação do canal no Youtube.

##### 3.2. Tabela de métricas
Dimensões: 1000 linhas x 5 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers/Year: Quantidade média de inscritos por ano no canal;
- Video Views/Year: Quantidade média de visualizações dos videos por ano no canal;
- Video Count/Year: Quantidade média de videos carregados no canal por ano;

#### 4. Most popular 1000 Youtube channels
> fonte: https://us.youtubers.me/global/all/top-1000-most-popular-youtube-channels

Apresenta um Top 1000 de canais do Youtube com maior popularidade.

##### 4.1. Tabela de dados
Dimensões: 1000 linhas x 7 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers: Quantidade de inscritos no canal;
- Video Views: Somatório de todas as visualizações dos videos do canal;
- Video Count: Quantidade de videos carregados no canal;
- Category: Categoria do conteúdo do canal;
- Started: Ano de criação do canal no Youtube.

##### 4.2. Tabela de métricas
Dimensões: 1000 linhas x 5 colunas

Colunas:
- Rank: Posição do canal no Top 1000;
- Youtuber: Nome do canal;
- Subscribers/Year: Quantidade média de inscritos por ano no canal;
- Video Views/Year: Quantidade média de visualizações dos videos por ano no canal;
- Video Count/Year: Quantidade média de videos carregados no canal por ano;

#### 5. Most popular 1000 Youtube videos
> fonte: https://us.youtubers.me/global/all/top-1000-most-popular-youtube-videos

Apresenta um Top 1000 de videos do Youtube com maior popularidade

##### 5.1. Tabela de dados
Dimensões: 1000 linhas x 7 colunas

Colunas:
- Rank: Posição do video no Top 1000;
- Video: Nome do video;
- Video Views: Quantidade de visualizações do video;
- Likes: Quantidade de likes do video;
- Dislikes: Quantidade de dislikes do video;
- Category: Categoria do conteúdo do video;
- Published: Ano em que o video foi publicado no Youtube.

##### 5.2. Tabela de métricas
Dimensões: 1000 linhas x 5 colunas:

Colunas:
- Rank: Posição do video no Top 1000;
- Video: Nome do video;
- Video Views/Year: Quantidade média de visualizações do video por ano;
- Likes/Year: Quantidade média de likes do video por ano;
- Dislikes/Year: Quantidade média de dislikes do video por ano.
