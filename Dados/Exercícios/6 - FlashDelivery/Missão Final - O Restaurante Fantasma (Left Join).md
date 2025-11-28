Para fechar a simulação da FlashDelivery, o Diretor Comercial está limpando a base de parceiros. Ele suspeita que temos restaurantes cadastrados que **nunca venderam nada**.

> _"Me dê uma lista com o **nome dos restaurantes** que estão cadastrados na plataforma, mas que **não têm nenhuma corrida** registrada no histórico."_

````
SELECT
	r.nome_restaurante,
	COUNT(id_corrida)
FROM
	Restaurantes AS r
LEFT JOIN
	Corridas AS c ON c.id_restaurante = r.id_restaurante
WHERE
	c.id_corrida IS NULL
GROUP BY
	r.nome_restaurante
```