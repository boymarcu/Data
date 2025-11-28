Agora que você sabe o que pode no `WHERE`, vamos testar isso num cenário com duas tabelas.

O Diretor quer saber:

> _"Quais são os **títulos das músicas** do gênero **'Rock'** e o **nome do artista** que as canta?"_

**O Cenário:**

- Tabela `Musicas`: tem `titulo`, `genero`, `id_artista`.
    
- Tabela `Artistas`: tem `nome`, `id_artista`.

````
SELECT
	a.nome,
	m.titulo
FROM 
	Artistas AS a
INNER JOIN
	Musicas AS m ON a.id_artista = m.id_artista
WHERE
	m.genero = 'Rock'
```