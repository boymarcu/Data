O time de Marketing quer premiar os usuários mais engajados.

> _"Quero saber quais **usuários** receberam mais **likes no total** (somando os likes de todos os seus posts). Mostre o **Nickname** e a **Quantidade Total de Likes Recebidos**, ordenando do maior para o menor."_

```
SELECT
    u.nickname,
    COUNT(l.id_like) AS Total_Likes_Recebidos 
FROM
    Usuarios AS u
INNER JOIN
    Posts AS p ON p.id_usuario = u.id_usuario
INNER JOIN
    Likes AS l ON l.id_post = p.id_post      
GROUP BY
    u.nickname                                
ORDER BY
    Total_Likes_Recebidos DESC;
```