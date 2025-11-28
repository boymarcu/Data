O Gerente de Operações quer saber qual tipo de veículo está rendendo mais dinheiro por entrega. Ele perguntou:

> _"Qual é a **Média do Valor do Frete** para cada **Tipo de Veículo**? Ordene do veículo que paga melhor para o que paga pior."_

````
SELECT
	AVG(c.valor_frete),
	e.veiculo
FROM
	Corridas AS c
INNER JOIN
	Entregadores AS e ON e.id_entregador = c.id_entregador
GROUP BY
	e.veiculo
ORDER BY
	AVG(c.valor_Frete) DESC
```