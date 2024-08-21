- **Projeto Conceitual** (Minimundo, Requisitos, Esquema Conceitual)
	- Independente da Classe do SGBD
	- Esquema conceitual
		- Modelos de dados de alto nível (como o modelo Entidade-Relacionamento)
- **Projeto Lógico**
	- Esquema lógico específico para uma Classe de SGBD 
		- Relacional
		- Hierárquico
		- O. Objeto...
- **Projeto Físico**
	- Esquema físico para um projeto físico específico
		- Oracle
		- SQL Server
		- MySQL
## Tipos de Mapeamento - Modelo ER -> BD Relacional
- Mapeamento de Entidade Regular
- Atributos Multivalorados
- Entidade Fraca
- Relacionamento Binário 1:1 
	- R.B. 1: N
	- R.B. N: N
- Relacionamento N-ário
	- Terciário
- Mapeamento de Generalização/Especialização
### Entidade Regular (Forte)
- Para cada entidade forte, criar uma tabela com todos os atributos.
- Escolher um **atributo** para ser a chave primária.
	- A chave primária pode ser composta.
### Atributos Multivalorados
- Criar tabela para atributo "Atributo"
- Incluir "Atributo" na tabela
- Incluir chave estrangeira (chave primária "CP" da Entidade ou relacionamento que tem "Atributo" como atributo).
- Chave primária = "Atributo" + "CP"
	- Tabela Cliente(<u>código</u>, Nome);
	- Tabela Telefone(<u>CodCliente</u>, Telefone);
	- <u>CodCliente</u> (FK) associada ao <u>CodCliente</u> (PK).
### Entidade Fraca
- Para cada entidade fraca que se liga a uma forte criar uma tabela e incluir todos os seus atributos.
- Incluir como FK as PK da tabela(s) da entidade proprietária.
- Chave Primária = Chave Primária da tabela proprietária + Chave Parcial da entidade fraca.
	- Tabela Empregado(<u>NEmp</u>, ...);
	- Tabela Dependente(<u>NEmp</u>, <u>CodDep</u>, NomeDep, DataNasc...);
	- Usar CASCADE ON UPDATE e ON DELETE para ação de disparo referencial na chave estrangeira da tabela da entidade fraca, devido à dependência de existência.
### Relacionamento 1:1
- Se escolhe usualmente uma das tabelas para incluir com FK a PK da outra.
- Escolher a entidade que tem participação total da outra.
	- Tabela Correntista(<u>Codigo</u>, ...);
	- Tabela CartaoMagnetico(<u>NumCartao</u>, DataExpiracao, Codigo(FK));
### Relacionamento 1:N
- Identificar a tabela B que representa a entidade do lado N do relacionamento
- Incluir na B a chave primária de A como FK
	- Tabela Departamento(<u>NDept</u>, NomeDept...);
	- Tabela Empregado(<u>NEmp</u>, NomeEmp, CargoEmp, NDept (FK));
### Relacionamento N:N
- Criar uma nova tabela para representar um relacionamento
- Incluir como colunas de chave estrangeira da tabela criada as chaves primárias das tabelas que representam as entidades participantes
- Chave primária = colunas das chaves estrangeiras
- Atributos do relacionamento N para N -> atributos da tabela criada
	- Tabela Empregado(<u>NEmp</u>, NomeEmp, ...);
	- Tabela Projeto(<u>NProj</u>, NomeProj, ...);
	- Alocacao(<u>NEmp (FK)</u>, <u>NProj(FK)</u>, HrsTrab);
### Relacionamento N-ário
- Criar nova tabela para relacionamento N-ário.
- Incluir como FK as PK de todas as tabelas (entidades) participantes.
- Incluir os atributos do relacionamento na tabela.
- Chave primária = combinação de todas as FK.
### Mapeamento Generalização-Especialização
- É uma implementação de herança.
- 1 OPÇÃO
	- Tabela para supertipo que absorve todos os atributos.
	- Acho menos elegante e pode nos fazer se perder em meio aos dados.
- 2 OPÇÃO
	- Tabelas representando os subtipos, sem uma tabela geral para os supertipos.
	- Implementa somente as especializações.
- 3 OPÇÃO
	- Tabelas representando cada entidade.
	- Os subtipos referênciam (FK) o super tipos pelo ID dele.


