Você é o mais novo Analista de Prevenção a Fraudes e Dados neste banco digital.

Aqui, lidamos com dinheiro. Seus dados precisam ser exatos. Um `JOIN` errado pode significar milhões perdidos ou clientes furiosos.

### 📂 O Banco de Dados (Schema Financeiro)

Analise as chaves e relacionamentos com atenção:

_(Imagine que o diagrama acima agora representa estas tabelas bancárias)_

**1. Tabela: `Clientes`**

- `id_cliente` (PK)
    
- `nome_completo` (Texto)
    
- `cpf` (Texto)
    
- `score_credito` (Inteiro - ex: 850)
    

**2. Tabela: `Contas`**

- `id_conta` (PK)
    
- `id_cliente` (FK - Liga com Clientes)
    
- `tipo_conta` (Texto - 'Corrente', 'Poupanca')
    
- `saldo_atual` (Decimal)
    

**3. Tabela: `Transacoes`** (O coração do banco)

- `id_transacao` (PK)
    
- `id_conta_origem` (FK - Quem pagou. Liga com Contas)
    
- `id_conta_destino` (FK - Quem recebeu. Liga com Contas)
    
- `valor` (Decimal)
    
- `data_hora` (Datetime)
    
- `tipo_transacao` (Texto - 'PIX', 'TED', 'Boleto')