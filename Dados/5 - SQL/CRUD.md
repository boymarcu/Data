## Os 4 Comandos Principais (CRUD)
CRUD significa **C**reate (Criar), **R**ead (Ler), **U**pdate (Atualizar), **D**elete (Deletar).

- `INSERT` (Criar)
    
- `SELECT` (Ler)
    
- `UPDATE` (Atualizar)
    
- `DELETE` (Deletar)


### `INSERT` (Criar)

Usado para adicionar uma nova linha (registro) a uma tabela.

```
INSERT INTO Funcionarios (ID, Nome, Cargo, Salario)
VALUES (5, 'Eduardo Paz', 'Estagiário', 1500);
```

_Agora, a tabela `Funcionarios` teria 5 linhas._


### `UPDATE` (Atualizar)

Usado para modificar dados em linhas existentes. **Sempre use `WHERE` com `UPDATE`!** Se você esquecer, atualizará _todas_ as linhas da tabela.

```
UPDATE Funcionarios
SET Salario = 4200
WHERE ID = 2;
```

_(O salário de Carlos Lima foi atualizado para 4200)._


#### `DELETE` (Deletar)

Usado para remover linhas. **Sempre use `WHERE` com `DELETE`!** Se esquecer, deletará _todas_ as linhas.
```
DELETE FROM Funcionarios
WHERE ID = 5;
```

_(O registro de Eduardo Paz foi removido)._




### Exemplos:

#### SELECT
- O comando `SELECT` é usado para buscar dados de uma tabela.

##### Selecionando Colunas Específicas

Vamos supor que temos uma tabela chamada `Funcionarios`:

| **ID** | **Nome**      | **Cargo**      | **Salario** |
| ------ | ------------- | -------------- | ----------- |
| 1      | Beatriz Costa | Desenvolvedora | 5000        |
| 2      | Carlos Lima   | Analista       | 4000        |
| 3      | Diana Alves   | Gerente        | 7000        |
| 4      | Bruno Gomes   | Desenvolvedor  | 5200        |

Para ver apenas o `Nome` e o `Cargo` de todos os funcionários:

```
SELECT Nome, Cargo
FROM Funcionarios;
```

**Resultado:** 
| Nome | Cargo | | :--- | :--- | 
| Beatriz Costa | Desenvolvedora | 
| Carlos Lima | Analista | 
| Diana Alves | Gerente | 
| Bruno Gomes | Desenvolvedor |


##### Selecionando Todas as Colunas

Para ver todas as informações da tabela, use o asterisco (`*`):

```
SELECT *
FROM Funcionarios;
```

**Resultado:** (A tabela inteira).


##### Filtrando Dados com `WHERE`

A cláusula `WHERE` é usada para filtrar linhas com base em uma condição.

**Exemplo 1: Encontrar funcionários com um cargo específico.**

```
SELECT Nome, Salario
FROM Funcionarios
WHERE Cargo = 'Desenvolvedora';
```

_Nota: Textos (strings) quase sempre usam aspas simples (`'`)._

**Resultado:** | Nome | Salario | | :--- | :--- | | Beatriz Costa | 5000 |


**Exemplo 2: Encontrar funcionários que ganham mais que 4500.**

```
SELECT Nome, Cargo, Salario
FROM Funcionarios
WHERE Salario > 4500;
```

**Resultado:** | Nome | Cargo | Salario | | :--- | :--- | :--- | | Beatriz Costa | Desenvolvedora | 5000 | | Diana Alves | Gerente | 7000 | | Bruno Gomes | Desenvolvedor | 5200 |


##### Ordenando os Resultados com `ORDER BY`

Você pode ordenar o resultado usando `ORDER BY`. 
O padrão é ascendente (`ASC`). Para descendente, use `DESC`.

**Exemplo: Listar funcionários do mais caro para o mais barato.**

```
SELECT Nome, Salario
FROM Funcionarios
ORDER BY Salario DESC;
```

**Resultado:** | Nome | Salario | | :--- | :--- | | Diana Alves | 7000 | | Bruno Gomes | 5200 | | Beatriz Costa | 5000 | | Carlos Lima | 4000 |


