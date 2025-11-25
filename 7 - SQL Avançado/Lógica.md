### Erro comum: SUM() na cláusula WHERE
- Inválido.
- O `WHERE`filtra linhas antes do agrupamento. Para filtrar agregações use `HAVING`.

### Definição: FULL OUTER JOIN
- Retorna a união completa:
  Interseção +  Exclusivos da Tabela A + Exclusivos da Tabela B.

### Definição: INNER JOIN
- Retorna apenas a interseção:
  Registros comuns a ambas as tabelas.

### Lógica: Coluna = 'A' AND Coluna = 'B'
- Resultado impossível (0 linhas).
- Uma célula não pode ter dois valores diferentes simultaneamente.

### Lógica: Coluna = 'A' OR Coluna = 'B'
- Retorna linhas que sejam 'A' ou 'B'.
- Equivalente a `IN ('A', 'B')`

### Função LEAD()
- Acessa o valor da linha SEGUINTE (futura) dentro da mesma partição/janela.

### Função DENSE_RANK()
- Ranking que **NÃO** deixa buracos na numeração após empates (1, 1, 2).

### Função RANK()
- Ranking que **DEIXA** buracos na numeração após empates (1, 1, 3). 

### Performance: UNION ALL vs UNION
- ``UNION ALL`` é mais rápido, pois não gasta recursos verificando e removendo duplicatas.

### Cláusula HAVING
- Filtra **grupos** de dados **APÓS** a execução do ``GROUP BY``.

### Cláusula WHERE
- Filtra **linhas individuais** **ANTES** da execução do ``GROUP BY``.

### Atalho par múltiplos OR
- Operador `IN`
  Ex: ``Cidade IN ('SP', 'RJ', 'MG)``

### Função LAG()
- Acessa o valor da linha **ANTERIOR** (passada) dentro da mesma partição/janela.

### Ordem de Execução Lógica (Resumo)
- FROM
- WHERE
- GROUP BY
- HAVING
- SELECT
- ORDER BY

### LEFT JOIN
- Retorna a Interseção + todos os registros da tabela da **ESQUERDA**
  Preenchendo direita com NULL se necessário.

### RIGHT JOIN
- Retorna a Interseção + todos os registros da **DIREITA**
  Preenchendo esquerda com NULL se necessário.

### Função ROW_NUMBER()
- Gera um número sequencial único para cada linha (1, 2, 3...), sem empates.

### INTERSECT
- Operador de conjunto que retorna apenas linhas existentes em **AMBOS** os resultados.

### Subquery no SELECT
- Deve retornar um único valor (escalar) para ser exibido como uma coluna.

### Subquery no FROM
- Atua como uma tabela temporária (Tabela Derivada) e exige um ALIAS (`AS`).

### PARTITION BY
- Divide o conjunto de resultados em janelas menores para cálculo independente de funções.
  Ex: Como reiniciar contagem por cliente.

### CROSS JOIN
- Produto Cartesiano.
- Combina cada linha de A com todas as linhas de B.

### COALESCE(val1, val2)
- Retorna o primeiro valor não nulo.
- Útil para tratar NULLs vindo de OUTER JOINs.

### SELF JOIN
- Uma tabela unida a si mesma
  Ex: Hierarquia Funcionário > Gerente.

### Operador EXISTS
- Retorna TRUE se a subconsulta retornar pelo menos uma linha.
- Muito eficiente para verificações