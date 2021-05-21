Aula SQL

### Tutorial SQL W3 w3schools
Aula: https://www.w3schools.com/sql/sql_exists.asp
Exercícios: https://www.w3schools.com/sql/exercise.asp?filename=exercise_select1


Começou a aula relembrando a aula da semana passada, onde foram obtidos dados através de um formulário no Google Forms. Esses dados foram armazenados em uma planilha


Vantagens e desvantagens de planilhas

Desvantagens
Limite na visualização dos dados das colunas
Limitação nas consultas, possibilita consultas mais simples

Vantagens
Facilidade de manuseio, carregamento, permite formulas


CSV
Não permite fórmulas, WYSWYG
Fácil de criar, human readable


#### Etapa 1
Baixa o CSV e utiliza python para manipular e limpar os dados
Os códigos utilizados para limpar os dados em CSV estão no arquivo compactado
na página do CS50 nomeado como src7.zip


#### Etapa 2
Importanto o arquivo CSV para o Sqlite
no terminal
sqlite3
.mode csv
<!-- Nome da função, nome do arquivo, nome da tabela -->
.import 'Favorite TV Shows - Form Responses 1.csv' shows

5 funções executam o CRUD de um banco de dados SQL. CREATE, INSERT, SELECT, UPDATE, DELETE.

- Lembrando que:
> CREATE é utilizado para criar novas tabelas e definir o tipo de dado de cada colunas
> INSERT é utilizado para popular uma tabela já criada

### Comandos no sqlite3
.open filename
.mode csv
.import nome_do_arquivo nome_da_tabela

O banco será carregado na memória. Para salvar:
.save nome_do_bd

.timer ON ou .timer OFF para retornar a duração da consulta.

### Funções no SQL
- AVG
- COUNT
- DISTINCT
- LOWER
- MAX
- MIN
- UPPER
- ...
> EXEMPLO:
```
SELECT DISTINCT(title) FROM shows;
```

### Clauses (Regras)
- WHERE  
- HAVING
- ORDER BY
- GROUP BY
- LIMIT

- ...
> EXEMPLO:
```
SELECT DISTINCT(title) FROM shows;
```

SELECT UPPER(TRIM(title)), COUNT(title) FROM shows GROUP BY UPPER(TRIM(title)) ORDER BY COUNT(title) DESC LIMIT 10;
