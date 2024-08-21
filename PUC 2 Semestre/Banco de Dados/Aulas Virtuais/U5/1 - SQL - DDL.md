## SQL 
- Linguagem padrão dos SGBD's que seguem o modelo relacional.
- Há variação - pequena - nela entre os fornecedores de SGBDs.
- Declarativa.
## DDL
- Parte da linguagem de BD destinada à manutenção das estruturas (tabelas, índices, visões).
	- CREATE, ALTER, DROP.
## Criação de Tabela (CREATE TABLE)
- Metadados são inseridos no dicionário de dados.
- Nome da tabela e lista de colunas com os tipos.
- Há restrições (constraint) particulares para algumas colunas e também para a tabela.
	- Constrainsts garantem que regras sejam aplicadas aos dados de uma tabela quando linhas são inseridas, apagadas ou modificadas.
```sql
CREATE TABLE nome_tabela 
(nome_coluna tipo_coluna [DEFAULT valor]
	CONSTRAINT nome_constraint tipo_constraint, 
	...)
```
O Microsoft SQL Server suporta vários tipos de dados, categorizados em diferentes grupos para armazenar diferentes tipos de informações. Aqui estão os principais tipos de dados no SQL Server:
### 1. Tipos de Dados Numéricos
- **Inteiros:**
  - `int`: Inteiro com tamanho fixo (4 bytes).
  - `bigint`: Inteiro grande (8 bytes).
  - `smallint`: Inteiro pequeno (2 bytes).
  - `tinyint`: Inteiro muito pequeno (1 byte).
- **Decimais e Numéricos:**
  - `decimal(p, s)`: Número com ponto decimal fixo.
  - `numeric(p, s)`: Sinônimo de `decimal`.
- **Precisão Flutuante:**
  - `float(n)`: Precisão flutuante (de 1 a 8 bytes).
  - `real`: Precisão flutuante (4 bytes).
### 2. Tipos de Dados de Cadeia de Caracteres
- **Cadeias de Caracteres de Comprimento Fixo:**
  - `char(n)`: Cadeia de caracteres com comprimento fixo.
  - `nchar(n)`: Cadeia de caracteres Unicode com comprimento fixo.
- **Cadeias de Caracteres de Comprimento Variável:**
  - `varchar(n)`: Cadeia de caracteres com comprimento variável.
  - `nvarchar(n)`: Cadeia de caracteres Unicode com comprimento variável.
- **Texto:**
  - `text`: Cadeia de caracteres de comprimento variável (descontinuado).
  - `ntext`: Cadeia de caracteres Unicode de comprimento variável (descontinuado).
### 3. Tipos de Dados Binários
- **Binários de Comprimento Fixo:**
  - `binary(n)`: Dados binários de comprimento fixo.
- **Binários de Comprimento Variável:**
  - `varbinary(n)`: Dados binários de comprimento variável.
  - `varbinary(max)`: Dados binários de comprimento variável até 2^31-1 bytes.
### 4. Tipos de Dados de Data e Hora
- `date`: Apenas data (sem hora).
- `time`: Apenas hora (sem data).
- `datetime`: Data e hora.
- `datetime2`: Data e hora com precisão maior.
- `smalldatetime`: Data e hora com precisão menor.
- `datetimeoffset`: Data e hora com fuso horário.
- `timestamp`: Marca temporal única para cada linha em uma tabela.
### 5. Tipos de Dados de Moeda
- `money`: Valores monetários.
- `smallmoney`: Valores monetários menores.
### 6. Tipos de Dados de Outros
- `bit`: Tipo booleano (0 ou 1).
- `uniqueidentifier`: Identificador único global (GUID).
- `sql_variant`: Armazena valores de vários tipos de dados.
- `xml`: Dados XML.
- `cursor`: Ponteiros para contextos de cursor.
- `table`: Tipo de dados especial usado para armazenar um conjunto de resultados temporários.
### Restrição de Chave Primária
- **PRIMARY KEY constraint:** garante integridade da entidade.
- Todas as colunas participantes de uma chave primária devem ser NOT NULL.
- Alguns SGBD's criam automaticamente um índice único (UNIQUE) para a chave primária.
### Restrição de Unicidade
- **UNIQUE constraint:** como uma tabela possui somente uma chave primária, podemos implementar as chaves candidatas ou únicas por meio desta restrição.
- Alguns SGBD's criam automaticamente um índice único (UNIQUE) para a restrição UNIQUE.
### Restrição de Chave Estrangeira
- **FOREIGN KEY constraint:** a chave estrangeira aponta para uma chave primária válida ou para NULL.
	- A tabela referenciada deve ter a chave primária já criada.
	- FK não permite o cadastro de um valor inexistente de chave primária.
	- **Relações Opcionais**: Permitir `NULL` em uma chave estrangeira é útil para modelar relações opcionais, onde a existência da relação não é obrigatória.
### Integridade Referencial Declarativa
```sql
[ON DELETE reference_option]
[ON UPDATE reference_option]

reference_option:
	RESTRICT 
	-- Não consegue excluir o Departamento 3, se houverem funcionários cadastrados.
	| CASCADE
	-- Se excluir o índice de Departamento 3, todos os funcionários são excluídos.
	| SET NULL 
	-- Departamento é settado para NULL
	| NO ACTION 
	-- Nada ocorre no Departamento.
	| SET DEFAULT
	-- Departamento recebe algum valor padrão.
```
### Restrição de DEFAULT
- **DEFAULT constraint:** especifica o valor default que será gravado em uma coluna quando o valor campo não for informado no momento do INSERT.
- Pode ser feito na frente do campo ou através de constraint.
### Restrição de Verificação
- **CHECK constraint(s):** define uma condição que cada coluna deve satisfazer.
	- Regra de negócio sobrepõe o valor de um campo.
		- Salário > salário_mínimo.
### Definição de Constraint
- Após todas as colunas.
- Pode se referir a mais de uma coluna.
	- Ex: PK composta.
## ALTER TABLE  
 Alteração da definição de uma tabela.
- Acrescentar coluna.
	- A coluna é adicionada no final da tabela.
	- Quando a tabela já possui registros incluídos, a nova coluna deve aceitar um default ou NULL.
-  Excluir coluna
- Alterar definição de coluna.
- Acrescentar **constraint** (restrição).
- Excluir constraint.
- Usar com moderação após população de dados. As vezes lógica do negócio já depende dessa base de dados.
## Drop Table
- Elimina a estrutura da tabela e todos os registros. USAR COM CUIDADO.
- Em alguns SGBD's todos os dados dependentes são excluídos (visões, índices)...
- DROP TABLE VS DELETE
	- DELETE é DML, DROP TABLE é DDL.
	- Delete somente exclui o conteúdo da tabela.
	- DropTable exclui o conteúdo e a estrutura.
- Ex: DROP TABLE Funcionarios;