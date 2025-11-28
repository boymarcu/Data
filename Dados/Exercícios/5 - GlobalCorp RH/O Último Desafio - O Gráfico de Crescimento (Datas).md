Para fechar sua passagem pelo RH com chave de ouro, o Diretor quer saber se a empresa está crescendo ou encolhendo.

> _"Eu quero saber **quantos funcionários** nós contratamos **por ano**. Mostre o Ano e a Quantidade de contratações."_

```
SELECT
    YEAR(data_contratacao) AS Ano,      
    COUNT(id_func) AS Contratos_Total  
FROM
    Funcionarios                        
GROUP BY
    YEAR(data_contratacao)              
ORDER BY
    Ano DESC;                           
```