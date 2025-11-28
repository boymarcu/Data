Agora que você tem os dados gerais, a segurança detectou um padrão estranho.

Existe um cliente específico que fez **muitas transações** pequenas num único dia, o que indica que ele pode ser um "Laranja" (alguém que recebe dinheiro picado para despistar).

**O Pedido:**

> _"Descubra o **Nome do Cliente** que realizou **mais de 5 transações** no dia **25/11/2025**. Mostre o nome dele e a contagem de transações."_


```
SELECT
    cl.nome_completo,
    COUNT(t.id_transacao) AS Qtd_Transacoes 
FROM
    Clientes AS cl
INNER JOIN
    Contas AS cc ON cc.id_cliente = cl.id_cliente
INNER JOIN
    Transacoes AS t ON t.id_conta_origem = cc.id_conta
WHERE
    DATE(t.data_hora) = '2025-11-25'
GROUP BY
    cl.nome_completo
HAVING
    COUNT(t.id_transacao) > 5;
```