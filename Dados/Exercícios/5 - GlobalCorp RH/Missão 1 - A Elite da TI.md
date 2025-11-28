O Diretor de Tecnologia quer rever os salários da equipe dele. Ele pediu:

> _"Me dê uma lista com o **nome** e o **salário** de todos os funcionários do departamento de **'Tecnologia'** que ganham **acima de R$ 8.000,00**. Por favor, ordene do maior salário para o menor."_

SQL

```
SELECT
    f.nome,
    f.salario     
FROM
    Funcionarios AS f
INNER JOIN
    Departamentos AS d ON d.id_depto = f.id_depto
WHERE
    d.nome_depto = 'Tecnologia'
    AND f.salario > 8000 
ORDER BY
    f.salario DESC;     
```