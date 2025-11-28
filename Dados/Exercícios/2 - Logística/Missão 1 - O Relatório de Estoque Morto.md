O Gerente de Estoque está preocupado com produtos que estão ocupando espaço e pegando poeira. Ele fez o seguinte pedido:

> _"Eu preciso de uma lista com o **nome dos produtos** que nós cadastramos no sistema, mas que **NUNCA foram vendidos** (ou seja, não aparecem em nenhum pedido)."_

````
SELECT
	p.nome_produto,
	i.id_produto
FROM
	Produtos AS p
LEFT JOIN
	Itens_Pedido AS i ON p.id_produto = i.id_produto
WHERE 
	i.id_pedido IS NULL
```