### 🏢 Bem-vindo à "GlobalCorp RH"

Você é o Analista de Dados do RH. Sua missão é ajudar a diretoria a entender custos, contratações e a estrutura da empresa.

### 📂 O Banco de Dados (Schema RH)

Temos apenas duas tabelas principais, mas elas respondem a muitas perguntas.

**1. Tabela: `Funcionarios`**

- `id_func` (PK - Identificador único)
    
- `nome` (Texto)
    
- `salario` (Decimal - ex: 4500.00)
    
- `data_contratacao` (Date - ex: '2023-05-20')
    
- `id_depto` (FK - Liga com a tabela de Departamentos)
    

**2. Tabela: `Departamentos`**

- `id_depto` (PK)
    
- `nome_depto` (Texto - ex: 'Marketing', 'TI', 'Vendas')