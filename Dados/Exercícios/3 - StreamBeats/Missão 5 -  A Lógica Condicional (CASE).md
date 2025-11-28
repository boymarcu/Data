Para fechar sua carreira na "StreamBeats", o Diretor de Produto quer categorizar as músicas para melhorar a recomendação.

Ele não quer apenas a duração em segundos. Ele quer uma coluna nova no relatório que diga **"Classificação"**:

- Se a música tiver **menos de 180 segundos** (3 min), chamar de **'Curta'**.
    
- Se tiver **300 segundos ou mais** (5 min), chamar de **'Longa'**.
    
- O resto, chamar de **'Média'**.
    

**O Cenário:**

- Tabela: `Musicas`.
    
- Colunas: `titulo`, `duracao_segundos`.
    
- Nova Coluna Calculada: `Classificacao`.

````
SELECT
	titulo,
	CASE
		WHEN duracao_segundos < 180 THEN 'Curta'
		WHEN duracao_segundos > 300 THEN 'Longa'
		ELSE 'Média'
    END AS 'Classificação'

FROM 
	Musicas
```