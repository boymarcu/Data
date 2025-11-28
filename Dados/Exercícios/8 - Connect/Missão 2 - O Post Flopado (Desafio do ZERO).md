O Diretor de Conteúdo quer identificar conteúdo ruim.

> _"Me dê uma lista dos **textos dos posts** (`texto_post`) que foram publicados, mas que **NÃO receberam nenhum like** até agora."_

```
SELECT
    p.texto_post,
    COUNT(l.id_like) AS Curtidas 
FROM
    Posts AS p
LEFT JOIN
    Likes AS l ON l.id_post = p.id_post
WHERE
    l.id_like IS NULL
GROUP BY
    p.texto_post;
```