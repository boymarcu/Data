- Realizam um cálculo sobre um conjunto de linhas e retornam um **único valor** (um resumo).

- `COUNT(*)`: Conta o número total de linhas.
- `SUM(coluna)`: Soma todos os valores de uma coluna numérica.
- `AVG(coluna)`: Calcula a média (Average) dos valores de uma coluna numérica.


#### `GROUP BY` (Agrupando Dados)

Isso é o que dá poder às funções de agregação. O `GROUP BY` é usado para "dividir" a tabela em grupos antes de aplicar as funções.

**O Problema:** E se eu não quiser o salário médio _da empresa inteira_, mas sim o salário médio _por cargo_?

**A Solução: `GROUP BY`**


#### `JOIN` (Combinando Tabelas)

Bancos de dados quase sempre têm múltiplas tabelas. O `JOIN` é usado para "juntar" tabelas com base em uma coluna em comum.

**O Problema:** Nossa tabela `Funcionarios` diz o cargo, mas não em qual _departamento_ o funcionário trabalha. Para organizar melhor, criamos uma _segunda tabela_.

**Tabela `Departamentos` (NOVA):**

| ID_Depto | Nome_Depto | Andar    |
| -------- | ---------- | -------- |
| 10       | Engenharia | 5° Andar |
| 20       | Finanças   | 3° Andar |

E agora, temos que "ligar" os funcionários a esses departamentos. Vamos adicionar a coluna `ID_Depto` na nossa tabela `Funcionarios`.

**Tabela `Funcionarios` (Atualizada para o `JOIN`):**

| ID  | Nome          | Salario | ID_Depto |
| --- | ------------- | ------- | -------- |
| 1   | Beatriz Costa | 5000    | 10       |
| 2   | Carlos Lima   | 4000    | 20       |
| 3   | Diana Alves   | 7000    | 10       |
| 4   | Bruno Gomes   | 5200    | 10       |

**Pergunta:** Como eu vejo o **Nome do Funcionário** e o **Nome do Departamento** em que ele trabalha, juntos?

**A Solução: `INNER JOIN`**

Você "junta" as duas tabelas ONDE (`ON`) as chaves se conectam (`Funcionarios.ID_Depto` = `Departamentos.ID_Depto`).

```
SELECT F.Nome, D.Nome_Depto, D.Andar
FROM Funcionarios AS F
INNER JOIN Departamentos AS D
    ON F.ID_Depto = D.ID_Depto;
```
**Resultado:**

| Nome          | Nome_Depto | Andar    |
| ------------- | ---------- | -------- |
| Beatriz Costa | Engenharia | 5º Andar |
| Diana Alve    | Engenharia | 5º Andar |
| Bruno Gomes   | Engenharia | 5º Andar |
| Carlos Lima   | Finanças   | 3º Andar |

O `INNER JOIN` só retorna as linhas onde há uma **correspondência exata** em AMBAS as tabelas.


#### `LEFT JOIN` (Foco na Esquerda)

O `LEFT JOIN` diz: "Mantenha **TODAS** as linhas da tabela da **ESQUERDA** (`Funcionarios`) e traga as correspondências da direita (`Departamentos`), se existirem. Se não existir correspondência, preencha com `NULL`."

```
SELECT F.Nome, D.Nome_Depto
FROM Funcionarios AS F
LEFT JOIN Departamentos AS D ON F.ID_Depto = D.ID_Depto;
```

**Resultado:**

| Nome           | Nome_Depto |
| -------------- | ---------- |
| Beatriz        | Engenharia |
| Carlos         | Finanças   |
| Diana          | Engenharia |
| Bruno          | Engenharia |
| **Fabio Reis** | **NULL**   |

_Repare: **Todos os funcionários (tabela da esquerda) apareceram.** O Fabio veio junto, mesmo sem ter um departamento. O Marketing (tabela da direita) não apareceu, pois nenhum funcionário "puxou" ele._

**Uso comum:** "Quero uma lista de _todos_ os funcionários e seus departamentos, _mesmo que_ eles ainda não tenham um departamento."



#### `RIGHT JOIN` (Foco na Direita)

O `RIGHT JOIN` é o oposto exato. Ele diz: "Mantenha **TODAS** as linhas da tabela da **DIREITA** (`Departamentos`) e traga as correspondências da esquerda (`Funcionarios`), se existirem. Se não existir correspondência, preencha com `NULL`."

SQL

```
SELECT F.Nome, D.Nome_Depto
FROM Funcionarios AS F
RIGHT JOIN Departamentos AS D ON F.ID_Depto = D.ID_Depto;
```

**Resultado:** 

| Nome     | Nome_Depto    |
| -------- | ------------- |
| Beatriz  | Engenharia    |
| Diana    | Engenharia    |
| Bruno    | Engenharia    |
| Carlos   | Finanças      |
| **NULL** | **Marketing** |

_Repare: **Todos os departamentos (tabela da direita) apareceram.** O Marketing veio junto, mesmo sem ter funcionários. O Fabio (tabela da esquerda) não apareceu, pois ele não tem um `ID_Depto` para "puxar" um departamento._

**Uso comum:** "Quero uma lista de _todos_ os departamentos e quantos funcionários eles têm, _mesmo que_ tenham zero funcionários."

_(Dica: A maioria dos programadores acha `RIGHT JOIN` confuso e prefere usar `LEFT JOIN` apenas invertendo a ordem das tabelas no `FROM`)._


#### Funções de Agregação (Irmãs do `SUM`/`AVG`)

- `MIN(coluna)`: Encontra o menor valor (Ex: `SELECT MIN(Salario) FROM ...`).
    
- `MAX(coluna)`: Encontra o maior valor (Ex: `SELECT MAX(Salario) FROM ...`).


#### Operadores Lógicos (Para o `WHERE`)

- `AND`: Para exigir que **duas condições** sejam verdadeiras.
    
    ```
    SELECT * FROM Funcionarios
    WHERE Cargo = 'Desenvolvedor' AND Salario > 5000;
    ```
    
- `OR`: Para exigir que **pelo menos uma condição** seja verdadeira.
    
    ```
    SELECT * FROM Funcionarios
    WHERE Cargo = 'Gerente' OR Cargo = 'Analista';
    ```
    

#### 3. Operadores de Comparação (Para o `WHERE`)

- `IN`: Uma forma limpa de escrever múltiplos `OR`.
    

    ```
    -- Isto é o mesmo que o exemplo do 'OR' acima:
    SELECT * FROM Funcionarios
    WHERE Cargo IN ('Gerente', 'Analista');
    ```
    
- `BETWEEN`: Para verificar se um valor está **dentro de um intervalo**.

    ```
    SELECT * FROM Funcionarios
    WHERE Salario BETWEEN 4000 AND 6000;
    ```
    
- `LIKE`: Usado para **buscar padrões em texto** (muito poderoso!).
    
    - `%` (coringa) significa "qualquer coisa".
        
    - `_` (coringa) significa "exatamente um caractere".
  
    ```
    -- Encontra qualquer pessoa cujo nome começa com 'B'
    SELECT * FROM Funcionarios WHERE Nome LIKE 'B%';
    
    -- Encontra qualquer pessoa cujo nome termina com 'Silva'
    SELECT * FROM Funcionarios WHERE Nome LIKE '%Silva';
    ```
    
- `IS NULL`: A forma correta de **verificar se um valor está vazio** (como o departamento do Fabio).
    
    - Você **não pode** usar `= NULL`. Tem que ser `IS NULL`.
    ```
    SELECT * FROM Funcionarios
    WHERE ID_Depto IS NULL;
    ```