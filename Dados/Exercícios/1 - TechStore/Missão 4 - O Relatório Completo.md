Para fechar sua primeira semana na "TechStore", vamos juntar tudo o que você aprendeu.

O Diretor quer um relatório para entender quem são nossos melhores compradores. Ele pediu:

> _"Quero uma lista com o **Nome do Cliente** e o **Valor Total Gasto** por ele em todos os pedidos que já fez. Mas atenção: mostre apenas os clientes que gastaram **mais de R$ 2.000,00 no total**."_

Calma! Não deixe seu cérebro derreter. 🤯 É super normal travar nessa query. Você tentou fazer tudo de uma vez (o que é ambicioso!), mas no SQL precisamos ser mais sequenciais.

Você acertou a **lógica das conexões** (sabia que precisava ligar `id_pedido` com `id_pedido` e `id_cliente` com `id_cliente`), o que é a parte mais difícil de visualizar. O erro foi apenas na **sintaxe** (como escrever isso).

Vamos desmontar sua query e montar a correta, peça por peça.

```
SELECT 
    c.nome,
    SUM(iP.quantidade * iP.preco_unitario) AS Valor_Total
FROM 
    Clientes AS c                 
INNER JOIN 
    Pedidos AS p                  
    ON c.id_cliente = p.id_cliente 
INNER JOIN 
    Itens_Pedido AS iP            
    ON p.id_pedido = iP.id_pedido  
GROUP BY 
    c.nome                   
HAVING 
    SUM(iP.quantidade * iP.preco_unitario) > 2000;
```