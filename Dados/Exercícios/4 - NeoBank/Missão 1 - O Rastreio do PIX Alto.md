O sistema de alerta apitou. Tivemos um volume suspeito de grandes transferências ontem.

O Gerente de Segurança pediu:

> _"Me dê uma lista de todas as **Transações do tipo 'PIX'** que foram **acima de R$ 10.000,00** realizadas no dia **25/11/2025**."_

```
SELECT
    cl.nome_completo,
    t.valor,
    t.data_hora
FROM
    Transacoes AS t
INNER JOIN
    Contas AS cc ON t.id_conta_origem = cc.id_conta
INNER JOIN
    Clientes AS cl ON cc.id_cliente = cl.id_cliente
WHERE
    t.valor > 10000
    AND t.tipo_transacao = 'PIX'        
    AND DATE(t.data_hora) = '2025-11-25';
```