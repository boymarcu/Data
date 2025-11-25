### Função da Cláusula WITH
- Define uma CTE (*Common Table Expression*), que age como uma tabela temporária para organizar a consulta.

### Diferença: WHERE vs HAVING
- `WHERE` filtra linhas (**ANTES de agrupar**).
- `HAVING` filtra grupos (**DEPOIS de agrupar**).

### Onde filtrar: Setor = 'Vendas'
- Cláusula `WHERE`
  Pois é um atributo da linha, não uma agregação.

### Onde filtrar: AVG(Salario) > 5000
- Cláusula `HAVING`
  Pois é resultado de uma função de agregação.

### Ordem Lógica de Execução
- FROM
- WHERE
- GROUP BY
- HAVING
- SELECT

### Vantagem da CTE sobre Subquery
- Melhora a legibilidade e organização, separando a lógica complexa do ``SELECT`` principal.

### Erro: WHERE SUM(VENDAS) > 100
- Inválido. O banco tenta filtrar antes de calcular a soma.
- Deve-se usar HAVING.

### Definição: LEFT JOIN
- Retorna a Interseção + todos os registros exclusivos da tabela da **ESQUERDA**.

### Definição: RIGHT JOIN
- Retorna a Interseção + todos os registros exclusivos da tabela da **DIREITA**.

### Definição: FULL OUTER JOIN
- Retorna TUDO: Interseção + Exclusivos da Direita + Exclusivos da Esquerda.

### Sintaxe da CTE
- `WITH NomeDaTabela AS (SELECT ...) SELECT ... FROM NomeDaTabela`.

### O que executa primeiro: SELECT ou GROUP BY
- `GROUP BY`.
- `SELECT` só escolhe as 'colunas' depois que os dados já foram processados.

### INNER JOIN
- Retorna apenas os registros que possuem correspondência em ambas as tabelas.

### Subquery na cláusula FROM
- Deve ter um ALIAS (``AS``) obrigatório.

### Lógica: Coluna = 'A' AND Coluna = 'B'
- Retorna zero linhas (impossível ser A e B ao mesmo tempo).

### Lógica: Coluna = 'A' OR Coluna = 'B'
- Retorna linhas que sejam 'A' ou 'B'.
- Equivalente a IN ('A', 'B').

### UNION ALL
- Combina resultados mantendo duplicatas (mais rápido).

### UNION
- Combina resultados removendo duplicatas (mais lento).

### Função ROW_NUMER()
- Gera um ranking sequencial único (1,2,3...) para cada linha.

### Função LAG()
- Acessa o valor da linha **ANTERIOR** na mesma janela.

### Função LEAD()
- Acessa o valor da linha **SEGUINTE** na mesma janela.

### Significado da linha CTE
- *Common Table Expression*

### Preenchimento em Outer Joins
- Usa-se ``NULL`` quando não há correspondência na outra tabela.

### Comando para eliminar tabela
- ``DROP TABLE``

### Comando para esvaziar tabela (rápido)
- ``TRUNCATE TABLE``