O CEO quer premiar o artista mais popular da plataforma. Ele pediu:

> _"Quero um ranking com o **Nome do Artista** e o **Total de Plays** (quantas vezes suas músicas foram tocadas no total). Ordene do mais ouvido para o menos ouvido."_

```
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
ORDER BY
    COUNT(h.id_play) DESC;
```