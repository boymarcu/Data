O time de segurança suspeita que criminosos estão usando contas do tipo **'Poupanca'** para girar dinheiro rápido via PIX, o que não é o comportamento normal de quem poupa.

O Gerente pediu:

> _"Quero ver o volume total de dinheiro (Soma do Valor) transacionado via **'PIX'**, quebrado por **Tipo de Conta** (Corrente vs Poupanca)."_

SQL

```
SELECT
    cc.tipo_conta,              
    SUM(t.valor) AS Volume_Total 
FROM
    Transacoes AS t
INNER JOIN
    Contas AS cc ON t.id_conta_origem = cc.id_conta
WHERE
    t.tipo_transacao = 'PIX'    
GROUP BY
    cc.tipo_conta               
ORDER BY
    Volume_Total DESC;          
```