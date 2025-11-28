O Diretor gostou da lista, mas agora ele quer saber **o que** foi vendido.

> _"Pegue o **Pedido #105** (id_pedido = 105). Eu quero saber o **nome dos produtos** que estão dentro desse pedido."_


```
SELECT 
    iP.id_pedido, 
    p.nome_produto
FROM 
    Itens_Pedido AS iP
INNER JOIN 
    Produtos AS p ON iP.id_produto = p.id_produto
WHERE 
    iP.id_pedido = 105;
```