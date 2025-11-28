### Bem-vindo ao "Hospital Santa Vida"

Você é o novo Analista de Dados Clínicos. O hospital precisa otimizar o atendimento, entender quais especialidades estão sobrecarregadas e identificar pacientes recorrentes.

### 📂 O Banco de Dados (Schema Hospitalar)

Temos 3 tabelas principais. Observe bem as chaves estrangeiras (`FK`).

_(Imagine que o diagrama acima representa as tabelas abaixo)_

**1. Tabela: `Pacientes`**

- `id_paciente` (PK)
    
- `nome_paciente` (Texto)
    
- `data_nascimento` (Date - ex: '1980-05-20')
    
- `genero` (Texto - 'M', 'F')
    

**2. Tabela: `Medicos`**

- `id_medico` (PK)
    
- `nome_medico` (Texto)
    
- `especialidade` (Texto - ex: 'Cardiologia', 'Ortopedia', 'Pediatria')
    

**3. Tabela: `Consultas`** (Onde tudo acontece)

- `id_consulta` (PK)
    
- `id_paciente` (FK)
    
- `id_medico` (FK)
    
- `data_hora` (Datetime)
    
- `valor` (Decimal - Quanto custou, se for particular)
    
- `status` (Texto - 'Realizada', 'Cancelada', 'Agendada')