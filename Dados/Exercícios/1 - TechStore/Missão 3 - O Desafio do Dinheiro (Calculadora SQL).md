Agora que você sabe quais produtos estão no pedido 105, o Diretor Financeiro apareceu. Ele não quer saber os nomes dos produtos, ele quer saber **quanto dinheiro** esse pedido gerou.

Na tabela `Itens_Pedido`, temos:

- `quantidade` (quantos itens comprou)
    
- `preco_unitario` (quanto custou cada um)
    

**Sua tarefa:** Calcule o **Valor Total** do Pedido 105.

```
SELECT
    SUM(quantidade * preco_unitario) AS Valor_Total
FROM
    Itens_Pedido
WHERE
    id_pedido = 105;
```