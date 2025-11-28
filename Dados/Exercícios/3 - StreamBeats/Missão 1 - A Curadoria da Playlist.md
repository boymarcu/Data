O Editor de Playlists quer criar uma lista chamada **"Curtinhas e Rápidas"**. Ele precisa filtrar o catálogo.

> _"Eu quero uma lista com o **título** e o **gênero** de todas as músicas que tenham **menos de 2 minutos e meio** (150 segundos) de duração. Ah, e ordene da mais curta para a mais longa, por favor."_

````
SELECT
	titulo,
	genero,
	duracao_segundos

FROM
	Musicas
WHERE
	duracao_segundos < 150
ORDER BY
	duracao_segundos ASC
```