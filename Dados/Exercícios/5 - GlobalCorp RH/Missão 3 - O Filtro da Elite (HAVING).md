O Diretor Financeiro olhou para o relatório que você acabou de gerar e franziu a testa.

> _"Tem departamento demais nessa lista. Eu quero focar minha atenção apenas nos departamentos onde a **Média Salarial** é muito alta. Filtre essa lista para mostrar apenas os departamentos onde a média (`AVG`) ganha **mais de R$ 6.000,00**."_


````
SELECT
	d.nome_depto,
	AVG(f.salario) AS Gasto_Total
FROM
	Funcionarios AS f
INNER JOIN
	Departamentos AS d ON d.id_depto = f.id_depto
GROUP BY
	d.nome_depto
HAVING
	AVG(f.salario) > 6000
```