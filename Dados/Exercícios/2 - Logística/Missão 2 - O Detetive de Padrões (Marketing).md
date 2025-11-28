O time de Marketing voltou. Eles estão criando uma campanha focada no público **Gamer**.

Eles querem saber:

> _"Qual é o **preço médio** dos nossos produtos que têm a palavra **'Gamer'** no nome?"_

**O Cenário:**

- Você vai trabalhar apenas com a tabela `Produtos`.
    
- Você precisa filtrar os nomes. Mas cuidado: o nome pode ser "Mouse Gamer", "Cadeira Gamer Pro", "Teclado Gamer Mecânico". A palavra "Gamer" pode estar no começo, no meio ou no fim.
    
- Depois de filtrar, você precisa calcular a média do preço.

```
SELECT
    AVG(preco) AS Valor_Medio
FROM
    Produtos
WHERE
    nome_produto LIKE '%Gamer%';
```