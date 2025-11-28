Você é o Analista de Dados da "Connect", uma rede social em crescimento. O desafio aqui não é valor monetário, é **interação**.

### 📂 O Banco de Dados (Schema Social)

Atenção especial para a tabela de `Seguidores`, que é puramente relacional.

_(Imagine que o diagrama acima representa estas tabelas)_

**1. Tabela: `Usuarios`**

- `id_usuario` (PK)
    
- `nickname` (Texto - ex: '@joao_dev')
    
- `pais` (Texto)
    

**2. Tabela: `Posts`**

- `id_post` (PK)
    
- `id_usuario` (FK - Quem escreveu)
    
- `texto_post` (Texto)
    
- `data_publicacao` (Date)
    

**3. Tabela: `Likes`** (Quem curtiu o quê)

- `id_like` (PK)
    
- `id_post` (FK - Qual post recebeu o like)
    
- `id_usuario` (FK - Quem deu o like)