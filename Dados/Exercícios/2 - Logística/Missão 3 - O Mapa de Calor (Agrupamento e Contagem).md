ara fechar sua contratação simbólica, o Diretor de Expansão quer saber onde focar a abertura de lojas físicas.

> _"Eu preciso saber **quantos clientes** nós temos em **cada estado**."_

**O Cenário:**

- Tabela: `Clientes`.
    
- Colunas: `id_cliente`, `estado`.

````
SELECT
	estado,
	COUNT(id_cliente)
FROM
	Clientes
GROUP BY
	estado
```