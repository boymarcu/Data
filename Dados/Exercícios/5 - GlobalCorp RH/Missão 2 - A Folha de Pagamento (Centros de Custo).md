O Diretor Financeiro entrou na sala. Ele precisa saber onde o dinheiro está indo.

> _"Eu preciso saber qual é o **Custo Total Mensal** (Soma dos Salários) de **cada departamento**. Quero uma lista com o nome do departamento e o valor total gasto com salários nele."_

````
SELECT
	d.nome_depto,
	SUM(f.salario) AS Gasto_Total
FROM
	Funcionarios AS f
INNER JOIN
	Departamentos AS d ON d.id_depto = f.id_depto
GROUP BY
	d.nome_depto
```