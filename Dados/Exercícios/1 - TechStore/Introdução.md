Vamos iniciar uma **Simulação de Caso Real**.

Imagine que você acabou de ser contratado como Analista de Dados Júnior na **"TechStore"**, um e-commerce de eletrônicos.

### 📂 O Cenário e o Banco de Dados

Aqui está a estrutura do banco de dados da empresa (o "Schema") com o qual você vai trabalhar. Analise as tabelas e como elas se relacionam:

**1. Tabela: `Clientes`**

- `id_cliente` (PK - Inteiro)
    
- `nome` (Texto)
    
- `email` (Texto)
    
- `estado` (Texto - ex: 'SP', 'RJ')
    

**2. Tabela: `Produtos`**

- `id_produto` (PK - Inteiro)
    
- `nome_produto` (Texto)
    
- `categoria` (Texto - ex: 'Notebooks', 'Periféricos')
    
- `preco` (Decimal)
    

**3. Tabela: `Pedidos`**

- `id_pedido` (PK - Inteiro)
    
- `id_cliente` (FK - Inteiro)
    
- `data_pedido` (Date)
    
- `status` (Texto - ex: 'Concluido', 'Cancelado')
    

**4. Tabela: `Itens_Pedido`** (Tabela de ligação)

- `id_pedido` (FK - Inteiro)
    
- `id_produto` (FK - Inteiro)
    
- `quantidade` (Inteiro)
    
- `preco_unitario` (Decimal - preço no momento da venda)