O Diretor Clínico quer fazer uma campanha preventiva. Ele precisa de uma lista simples.

> _"Quero o **nome dos pacientes** que passaram em consulta com a especialidade **'Cardiologia'** no ano de **2024** e que a consulta foi **'Realizada'**."_


```
SELECT
    p.nome_paciente,
    COUNT(c.id_consulta) AS Qtd_Individual,
    SUM(COUNT(c.id_consulta)) OVER() AS Qtd_Total_Geral
FROM
    Pacientes AS p
INNER JOIN
    Consultas AS c ON c.id_paciente = p.id_paciente
INNER JOIN
    Medicos AS m ON c.id_medico = m.id_medico
WHERE
    m.especialidade = 'Cardiologia'
    AND YEAR(c.data_hora) = 2024
    AND c.status = 'Realizada'
GROUP BY
    p.nome_paciente;
``