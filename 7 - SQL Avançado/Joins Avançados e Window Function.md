### FULL OUTER JOIN
- Retorna **TODOS** os registros de ambas as tabelas (União ``LEFT``e``RIGHT``).
- Preenche com ``NULL``onde não há correspondência.

### Lógica do Operador IN('A', 'B')
- Equivalente lógico a condições ``OR (x = 'A' OR x = 'B').``
- Não é uma interseção.

### Função para ranquear/numerar linhas
- `ROW_NUMBER()`= Ideal par encontrar o 'primeiro' registro de um grupo.

### Função para acessar a linha anterior
- `LAG()`= Ideal para comparar valor atual com o passado. 

### Local correto para Subquery de filtro
- Cláusula `WHERE` = ex: `WHERE id IN (SELECT...)`

### LEFT JOIN (Conceito de Conjunto)
- Contém a **INTERSEÇÃO** + todos os registros exclusivos da tabela da **ESQUERDA**.

### INTERSECT
- Retorna apenas as linhas comuns a dois conjuntos de resultados (A e B).

### UNION ALL
- Combina resultados mantendo duplicatas
  (Mais rápido que o UNION).

### UNION
- Combina resultados removendo duplicatas (Mais lento, pois exige ordenação/distinct).

### Subquery no GROUP BY
- **PROIBIDO NOP PADRÃO SQL**;
- Não se pode definir o agrupamento dinamicamente via subquery.

### Cláusula PARTITION BY
- Reinicia a contagem/cálculo da função de janela para cada grupo específico.
  Ex: numerar compras por cliente.

### INNER JOIN
- Retorna apenas a INTERSEÇÃO.
  (Registros que existem em ambas as tabelas).

### RIGHT JOIN
- Retorna todos os registros da tabela da **DIREITA**, combinando com a esquerda quando possível (o oposto do **LEFT**).

### Função LEAD()
- Acessa dados da linha SEGUINTE (futura) na mesma janela.

### Diferença: WHERE vs HAVING
- ``WHERE`` filtra *linhas* (**antes de agrupar**).
- `HAVING` filtra *grupos* (**depois de agrupar**).

### Uso de ALIAS em Subqueries
- **Obrigatório** quando a subquery está na cláusula **FROM** (tabela derivada).

### CROSS JOIN
- Produto Cartesiano.
- Combina cada linha de A com todas as linhas de B (sem condição ON).

### Função COALESCE(val1, val2)
- Retorna o primeiro valor não nulo. 
- Útil para substituir NULLs gerados por Outer Joins.

### Predicado EXISTS
- Verifica se uma subquery retorna *algum* resultado.
- Geralmente mais performático que ``IN`` para subqueries grandes.

### SELF JOIN
- Uma tabela unida a ela mesma.
- Útil para estruturas hierárquicas (ex: Funcionário > Gerente na mesma tabela).

### RANK() vs DENSE_RANK()
- `RANK` pula números após empates (1, 1, 3).
- `DENSE_RANK` não pula (1, 1, 2).

### Ordem de Escrita vs Execução
- Escrita: 
  - SELECT ...
  - FROM ...
  - WHERE .
- Execução
  - FROM ...
  - WHERE ...
  - SELECT.

### Função de Agregação vs Janela
- Agregação (`SUM`) reduz linhas.
- Janela (`SUM OVER`) mantém as linhas originais e adiciona o cálculo.

### CASE WHEN
- Estrutura condicional (`If-Else`) dentro de uma query para transformar dados.

### DELETE vs TRUNCATE
- `DELETE`é logado e reversível (lento).
- `TRUNCATE` reseta a tabela (rápido DDL).