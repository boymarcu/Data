Agora que você já tem o ranking, o Diretor de Marketing quer filtrar essa lista. Ele diz:

> _"Essa lista está muito grande. Eu quero ver **apenas** os artistas que já passaram de **1 milhão de plays** (Total_Plays > 1000000)."_

**O Cenário:**

- É exatamente a mesma query que você acabou de fazer.
    
- Você só precisa adicionar um filtro.
    

**A Pergunta de 1 Milhão de Dólares:** Onde você coloca esse filtro `> 1000000`?

1. No `WHERE`?
    
2. No `HAVING`?

````
SELECT 
	a.nome,
	COUNT(h.id_play) AS Total_Plays
FROM
	Artistas AS a
INNER JOIN
	Musicas AS m ON m.id_artista = a.id_artista
INNER JOIN
	Historico_Plays AS h ON h.id_musica = m.id_musica
GROUP BY
	a.nome
HAVING
	Total_Plays > 1000000
ORDER BY
	Total_Plays DESC
```