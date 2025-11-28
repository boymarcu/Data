
```
WITH TopMusicas AS (
    SELECT
        titulo,
        genero,
        duracao_segundos,
        ROW_NUMBER() OVER (
            PARTITION BY genero
            ORDER BY duracao_segundos DESC
        ) AS Ranking
    FROM
        Musicas
)
SELECT *
FROM 
	TopMusicas
WHERE 
	Ranking = 1;
```