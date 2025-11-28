### 1. A Ordem Sagrada da Query

O banco lê seu código nesta ordem (decore isso para debugar erros):

1. `FROM` & `JOIN` (Pega as tabelas)
    
2. `WHERE` (Filtra as linhas originais)
    
3. `GROUP BY` (Agrupa em pilhas)
    
4. `HAVING` (Filtra as pilhas/agrupamentos)
    
5. `SELECT` (Escolhe as colunas e cria apelidos)
    
6. `ORDER BY` (Arruma a ordem final)
    

### 2. Tipos de JOIN (As Conexões)

- **`INNER JOIN`**: "O Casal Perfeito". Só traz dados se existirem nas duas tabelas.
    
- **`LEFT JOIN`**: "O Solteiro Incluso". Traz tudo da esquerda, mesmo se não tiver par na direita (preenche com NULL).
    
- **`LEFT JOIN` + `IS NULL`**: "O Solitário". Traz apenas o que NÃO tem par na outra tabela (ex: Produtos sem Vendas).
    

### 3. Agregações (A Matemática)

Sempre exigem `GROUP BY` se houver outras colunas no SELECT.

- `COUNT(*)`: Conta linhas.
    
- `SUM(coluna)`: Soma valores.
    
- `AVG(coluna)`: Média.
    
- `MAX(coluna)` / `MIN(coluna)`: Maior / Menor valor.
    

### 4. Filtros (O Porteiro)

- **Texto Parcial:** `WHERE nome LIKE '%Silva%'`
    
- **Listas:** `WHERE estado IN ('SP', 'RJ', 'MG')`
    
- **Datas:** `WHERE YEAR(data) = 2024`
    

### 5. Truques Avançados (Nível Sênior)

- **Categorizar:** `CASE WHEN valor > 10 THEN 'Alto' ELSE 'Baixo' END`
    
- **Ranking:** `ROW_NUMBER() OVER (PARTITION BY categoria ORDER BY valor DESC)`
    
- **CTE (Organização):**
    ```
    WITH TabelaTemporaria AS (
        SELECT ...
    )
    SELECT * FROM TabelaTemporaria...
    ```