# SQL

## Instruções comuns

| Instrução | Descrição                                                          |
| --------- | ------------------------------------------------------------------ |
| `SELECT`  | Seleciona os dados no banco de dados (colunas, por exemplo)        |
| `AS`      | Renomeia uma coluna ou tabela durante a execução do script         |
| `FROM`    | Especifica a tabela de origem dos dados                             |
| `WHERE`   | Filtra a consulta com uma condição                                 |
| `JOIN`    | Combina duas ou mais tabelas                                       |
| `AND`     | Condicional "E" para consultas                                     |
| `OR`      | Condicional "OU" para consultas                                    |
| `LIKE`    | Busca por "_patterns_" em uma coluna                               |
| `IN`      | Especifica um conjunto de valores ao para serem usados por `WHERE`  |
| `IS NULL` | Comparativo de nulidade de uma linha, coluna ou célula             |
| `LIMIT`   | Limita a quantidade de linhas retornadas                           |
| `CASE`    | Valor de retorno em uma condição especificada                       |

## Alterações em tabelas

| Instrução     | Descrição                                                                                      |
| ------------- | ---------------------------------------------------------------------------------------------- |
| `CREATE`      | Cria tabela (`TABLE`), index (`INDEX`), banco de dados (`DATABASE`) ou visualização (`VIEW`)   |
| `DROP`        | Exclui tabela (`TABLE`), index (`INDEX`), banco de dados (`DATABASE`) ou visualização (`VIEW`) |
| `UPDATE`      | Atualiza dados em uma tabela selecionada                                                       |
| `DELETE`      | Exclui linhas de uma tabela                                                                    |
| `ALTER TABLE` | Adiciona e/ou remove colunas de uma tabela                                                     |

## Tratamento de resultados

| Instrução  | Descrição                                               |
| ---------- | ------------------------------------------------------- |
| `GROUP BY` | Agrupa linhas a partir de um valor                      |
| `ORDER BY` | Ordena as linhas de acordo com um valor                 |
| `HAVING`   | Similar ao `WHERE`, mas usado para funções de agregação |
| `SUM`      | Retorna a soma da coluna                                |
| `AVG`      | Retorna a média da coluna especificada                   |
| `MIN`      | Retorna o valor mínimo da coluna                        |
| `MAX`      | Retorna o valor máximo da coluna                        |
| `COUNT`    | Retorna a contagem de linhas                            |

## Exemplos

Criar base de dados:

```SQL
CREATE DATABASE meuDatabase;
```

---

Deletar base de dados:

```SQL
DROP TABLE meuDatabase;
```

---

Atualizar uma tabela:

```SQL
UPDATE 
    meuDatabase;
SET 
    coluna_01 = 100;
WHERE
    coluna_02 = "Algum valor aqui";
```

---

Seleciona linhas de tabelas usando um filtro:

```SQL
SELECT *
FROM
 meuDatabase.minhaTabela
WHERE
 coluna_01 > 100;
```

ou:

```SQL
USE meuDatabase;
SELECT *
FROM
 minhaTabela
WHERE
 coluna_01 > 100;
```

---

Selecionando as primeiras 10 linhas de uma consulta:

```SQL
SELECT
    coluna_01, coluna_02
FROM
    minhaTabela
LIMIT 10;
```

---

Combinando duas tabelas:

```SQL
SELECT *
FROM
    coluna_01 AS tb1
LEFT JOIN
    tabela_02 AS tb2
    ON tb2.coluna_01 = tb1.coluna_01;
```
