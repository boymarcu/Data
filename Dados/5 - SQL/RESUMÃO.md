## **Nível 1: O Básico (Consultas Simples)**

1. **O que é um Banco de Dados Relacional?** Entenda o que é uma tabela (table), coluna (column), linha (row) e chave primária (primary key).
    
2. **`SELECT` e `FROM`:** A base de tudo. Como "ler" dados.
    
    - `SELECT nome, email FROM usuarios;`
        
3. **`WHERE`:** Como filtrar seus dados.
    
    - `SELECT * FROM produtos WHERE preco < 100;`
        
4. **`ORDER BY`:** Como ordenar os resultados (ascendente `ASC` e descendente `DESC`).
    
    - `SELECT * FROM produtos ORDER BY preco DESC;`
        
5. **`LIMIT`:** Como limitar o número de resultados (ótimo para paginação).
    
    - `SELECT * FROM produtos ORDER BY preco DESC LIMIT 10;`

## **Nível 2: Manipulação e Agregação de Dados**

1. **`INSERT`, `UPDATE`, `DELETE`:** Como criar, atualizar e deletar dados. (O "CUD" do CRUD).
    
2. **Funções de Agregação:** Ferramentas essenciais para análise de dados.
    
    - `COUNT()` (contar linhas)
        
    - `SUM()` (somar valores)
        
    - `AVG()` (calcular média)
        
    - `MIN()` / `MAX()` (encontrar o menor/maior valor)
        
3. **`GROUP BY`:** O parceiro das funções de agregação. Como agrupar resultados.
    
    - _Ex: "Qual a média de preço POR categoria de produto?"_
        
    - `SELECT categoria, AVG(preco) FROM produtos GROUP BY categoria;`

## **Nível 3: O Conceito Mais Importante (JOINs)**

1. **Chaves Estrangeiras (Foreign Keys):** Entenda como as tabelas se relacionam.
    
2. **`JOIN`s:** Como combinar dados de múltiplas tabelas.
    
    - `INNER JOIN` (O mais comum: pega apenas o que existe nas duas tabelas).
        
    - `LEFT JOIN` (Pega tudo da tabela da "esquerda" e combina com o que existir na "direita").
        
    - `RIGHT JOIN` e `FULL OUTER JOIN` (conceitos complementares).

## **Nível 4: Tópicos Avançados para o Domínio**

11. **Subqueries (Subconsultas):** Uma consulta dentro de outra consulta.
    
12. **`CASE`:** Como usar lógica condicional (if/else) dentro do seu `SELECT`.
    
13. **DDL (Data Definition Language):** Comandos para _estruturar_ o banco.
    
    - `CREATE TABLE` (criar tabela)
        
    - `ALTER TABLE` (modificar tabela)
        
    - `DROP TABLE` (excluir tabela)