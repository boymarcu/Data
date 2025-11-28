O Diretor Comercial chegou na sua mesa e disse:

> _"Precisamos focar nossa campanha de marketing. Eu quero saber **quais clientes do estado de 'SP' fizeram pedidos que foram concluídos** (status = 'Concluido'). Quero apenas o nome do cliente e o ID do pedido, para conferência."_

**Sua tarefa:** Escreva a query SQL para extrair esses dados.


`SELECT`
    `C.nome,`
    `P.id_pedido`
`FROM`
    `Clientes AS C`
`INNER JOIN`
    `Pedidos AS P ON C.id_cliente = P.id_cliente`
`WHERE`
    `C.estado = 'SP'`
    `AND P.status = 'Concluido';`