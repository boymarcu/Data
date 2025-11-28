Agora vamos complicar um pouco a logística. O dono de uma rede de comida japonesa quer fazer uma parceria exclusiva. Ele perguntou:

> _"Quem é o entregador que mais realizou entregas para restaurantes da categoria **'Japonesa'**? Quero o nome dele e a quantidade de entregas."_

SQL

```
SELECT
    e.nome,
    COUNT(c.id_corrida) AS Total_Entregas
FROM
    Corridas AS c
INNER JOIN
    Entregadores AS e ON e.id_entregador = c.id_entregador
INNER JOIN
    Restaurantes AS r ON r.id_restaurante = c.id_restaurante
WHERE
    r.categoria = 'Japonesa'
GROUP BY
    e.nome
ORDER BY
    Total_Entregas DESC;
```