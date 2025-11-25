### Diferença: UNION vs UNION ALL
- ``UNION`` **remove** duplicatas (processamento extra).
- ``UNION ALL`` **mantém** duplicatas (processamento mais rápido).

### Definição: FULL OUTER JOIN
- Retorna TODOS os registros de ambas as tabelas.
- Preenche com NULL onde não houver correspondência.

### Operador INTERSECT
- Retorna apenas as linhas que existem em AMBOS os conjuntos de resultados (A e B).

### Função ROW_NUMBER()
- Gera um número sequencial único (1, 2, 3...) para cada linha dentro de uma partição.

### Função LAG()
- Acessa dados da linha ANTERIOR na mesma janela.
  (Útil para comparar crescimento/mudança).

### Onde NÃO usar Subqueries (Padrão SQL)
- Diretamente na cláusula `GROUP BY`.

### Subquery Correlacionada
- Uma subquery que referencia colunas da query externa e é executada repetidamente (linha por linha).

### Requisito de Subquery no FROM
- Deve ter um ALIAS (nome temporário para a tabela derivada).

### Objetivo do EXISTS
- Verificar se uma subquery retorna *algum* resultado.
- Retorna TRUE/FALSE e para assim que acha o primeiro registro.

### Estrutura do CASE
- ``CASE WHEN`` condição
- `THEN` resultado
- ``ELSE`` outro_resultado
- `END` 

### Cláusula PARTITION BY (Window Functions)
- Divide o conjunto de resultados em partições *(grupos)* onde a função de janela é aplicada separadamente (como um ``GROUP BY`` local).

### LEFT JOIN vs FULL JOIN
- `LEFT` traz tudo da esquerda + **matches** da direita.
- ``FULL`` traz tudo da esquerda + tudo da direita **(união completa)**.

### Operador EXCEPT (ou MINUS)
- Retorna linhas do primeiro conjunto que NÃO existem no segundo conjunto.

### Performance: Subquery Correlacionada
- Geralmente lenta em grandes volumes, pois executa N vezes.
  (Onde N é o número de linhas da query externa).

### Subquery Escalar
- Um subquery que retorna exatamente um valor (uma linha, uma coluna).
- Pode ser usada no ``SELECT`` ou ``WHERE``.

### CTE (Common Table Expression)
- Uma 'tabela temporária' definida com ``WITH`` antes do ``SELECT`` principal.
- Mais legível que subqueries no ``FROM``.

### Função RANK() vs ROW_NUMBER()
- `ROW_NUMBER()` sempre dá n°s únicos.
- `RANK` repete o n° em caso de empate e pula o próximo (ex: 1, 1, 3).

### Cross Join
- Produto Cartesiano.
- Combina cada linha da tabela A com cada linha da tabela B.

### COALESCE(coluna, valor)
- Retorna o primeiro valor não nulo da lista. 
- Útil para substituir NULLs por 0 ou texto padrão.

### Self Join
- Quando uma tabela faz JOIN com ela mesma.
- (Útil para hierarquias, ex: Funcionário e Gerente na mesma tabela).

### HAVING com Subquery
- É permitido.
- Ex: Filtrar grupos cuja soma de vendas seja maior que a média geral (calculada via subquery).

### IN vs EXISTS (Tratamento de NULL)
- `NOT IN` falha se houver `NULL` na lista da subquery.
- `NOT EXISTS` lida com `NULL`de forma mais segura.

### Ordem no UNION
- Para ordenar o resultado de um `UNION`, o  `ORDER BY` deve ir apenas no final da última query.

### Predicado lógico do SQL
- Lógica ternária: TRUE, FALSE e UNKNOW (NULL).

### Cláusula OVER()
- Define a 'janela' ou conjunto de linhas sobre o qual uma Window Function (como `ROW_NUMBER()` ou ``AVG``) irá operar.