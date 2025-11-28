Você agora é Analista de Dados em um aplicativo de streaming de música (concorrente do Spotify).

O negócio aqui não é mais "Vendas" e "Estoque". O foco agora é **Engajamento**, **Artistas** e **Reproduções (Plays)**.

### 📂 O Novo Banco de Dados

Analise com carinho, pois os nomes mudaram:

**1. Tabela: `Artistas`**

- `id_artista` (PK)
    
- `nome` (Texto - ex: 'Queen', 'Anitta')
    
- `pais` (Texto - ex: 'UK', 'Brasil')
    

**2. Tabela: `Musicas`**

- `id_musica` (PK)
    
- `titulo` (Texto - ex: 'Bohemian Rhapsody')
    
- `duracao_segundos` (Inteiro - ex: 354)
    
- `genero` (Texto - ex: 'Rock', 'Pop', 'Funk')
    
- `id_artista` (FK - Liga com a tabela Artistas)
    

**3. Tabela: `Usuarios`**

- `id_usuario` (PK)
    
- `nome` (Texto)
    
- `plano` (Texto - ex: 'Premium', 'Free')
    

**4. Tabela: `Historico_Plays`** (Onde a mágica acontece - quem ouviu o quê)

- `id_play` (PK)
    
- `id_usuario` (FK)
    
- `id_musica` (FK)
    
- `data_hora` (Datetime)