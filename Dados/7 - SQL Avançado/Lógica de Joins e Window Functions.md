### FULL OUTER JOIN
- Retorna **TODOS** os registros de ambas as tabelas
  (Interseção + Exclusivos A + Exclusivos B).

### Lógica do operador AND na mesma coluna
- Retorna zero linhas.
  (Uma coluna não pode ser 'A' e 'B' ao mesmo tempo).

### Função ROW_NUMBER()
- Atribui um ranking único (1, 2, 3...) para cada linha numa partição.

### Função LAG()
- Acessa o valor da linha **ANTERIOR** (atraso) na mesma janela.

### Local para filtrar grupos (pós-agregação)
- Cláusula `HAVING`.

### Local para filtrar linhas (pré-agregação)
- Cláusula `WHERE`.

### DENSE_RANK()
- Ranking que **NÃO** pula números após empates (1, 1, 2).

### RANK()
- Ranking que **PULA** números após empates (1, 1, 3).

### RIGHT JOIN
- Retorna a **Interseção** + todos os registros exclusivos da tabela da **DIREITA**.

### LEFT JOIN
- Retorna a **Interseção** + todos os registros exclusivos da tabela da **ESQUERDA**.

### Equivalência lógica de IN ('A', 'B')
- Condição `OR (x = 'A' OR X = 'B')`

### Uso de Subquery no FROM
- Define a fonte de dados (Tabela Derivada).
  Requer Alias (``as``).

### Uso de Subquery no WHERE
- Filtra linhas com base em resultados de outra query (`IN`, `EXIST`).

### Cláusula PARTITION BY
- Reinicia o cálculo da função de janela para cada grupo definido.

### UNION vs UNION ALL
- `UNION` remove duplicatas (lento).
- `UNION ALL` mantém tudo (rápido).

### Função LEAD()
- Acessa o valor da linha SEGUINTE (futura) na mesma janela.

### INNER JOIN
- Apenas a Interseção (registros comuns às duas tabelas).

### Comando par encontrar 'Primeiro registo'
- `ROW_NUMBER() OVER (ORDER BY ...)`

### INTERSECT
- Operador que retorna apenas linhas comuns a dois `SELECTs`

### EXCEPT / MINUS
- Retorna linhas do primeiro ``SELECT`` que não existem no segundo.

### CROSS JOIN
- Produto Cartesiano.
- (Todas as combinações possíveis).

### COALESCE()
- Retorna o primeiro valor não nulo (útil após `OUTER JOIN`).

### SELF JOIN
- Tabela unida a ela mesma (hierarquias).

### Subquery Correlacionada
- Executa repetidamente para cada linha da query externa.

### Preenchimento em Outer Joins
- `NULL` é usado onde não há correspondência na outra tabela.