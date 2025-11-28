Aqui está a estrutura focada no seu desafio atual (**Produtos** vs **Vendas**):

### 1. Tabela Principal

**Tabela: `Produtos`** (Onde estão todos os itens cadastrados)

- `id_produto` (PK - A chave que identifica o produto)
    
- `nome_produto`
    
- `categoria`
    
- `preco`
    

### 2. Tabela de Vendas

**Tabela: `Itens_Pedido`** (Onde ficam os registros de venda)

- `id_pedido` (FK)
    
- `id_produto` (FK - A chave que conecta com a tabela de produtos)
    
- `quantidade`
    
- `preco_unitario`