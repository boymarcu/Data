### Bem-vindo à "FlashDelivery"

Você é o novo Analista de Dados deste aplicativo de entregas (estilo iFood/Uber Eats).

Aqui, a diretoria quer otimizar a logística. Eles precisam saber quem corre mais, quem ganha mais e onde estão os gargalos.

### 📂 O Banco de Dados (Schema Logístico)

Temos 3 tabelas essenciais.

_(Imagine que o diagrama acima agora representa estas tabelas de logística)_

**1. Tabela: `Entregadores`**

- `id_entregador` (PK)
    
- `nome` (Texto)
    
- `veiculo` (Texto - ex: 'Moto', 'Bike', 'Carro')
    

**2. Tabela: `Restaurantes`**

- `id_restaurante` (PK)
    
- `nome_restaurante` (Texto - ex: 'Pizza King', 'Sushi House')
    
- `categoria` (Texto - ex: 'Lanches', 'Japonesa')
    

**3. Tabela: `Corridas`** (Cada entrega feita)

- `id_corrida` (PK)
    
- `id_entregador` (FK)
    
- `id_restaurante` (FK)
    
- `valor_frete` (Decimal - Quanto o entregador ganhou)
    
- `distancia_km` (Decimal - Distância percorrida)
    
- `status` (Texto - 'Concluido', 'Cancelado')