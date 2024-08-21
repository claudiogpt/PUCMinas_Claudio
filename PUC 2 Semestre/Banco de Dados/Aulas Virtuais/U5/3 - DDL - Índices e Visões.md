## ÍNDICES (CREATE INDEX)
- Estruturas físicas **opcionais** de banco de dados. 
- Criadas para melhorar a performance no acesso. 
- Alguns SGBD's criam automaticamente pelas chaves primárias e candidatas.
#### Uso
- Caberá ao otimizador do SGBD optar ou não pelo uso do índice (DML não-procedural).
- Na falta de índices, o SGBD faz uma varredura completa da tabela (**full table scan**).
- Os comandos SELECT que envolvem ORDER BY (ordenação) tendem a ficar mais rápidos após a criação de índices pelos campos de ordenação.
	- Os índices devem ser criados com prudência.
#### Escolha dos Índices
- Analisa-se quais campos da tabela participam de das expressões WHERE de comandos de SELECT, UPDATE e DELETE.
- O uso excessivo de índices pode prejudicar o desempenho
	- Todo comando que altera a tabela de origem (INSERT, UPDATE, DELETE) pode gerar uma alteração no índice.
	- Lembrando que índices são feitos para melhorar a performance do BD.
- Geralmente são definidos pelo DBA e pelo Dev., que conhecem as consultas mais críticas/frequentes
- Índices são parte importante do "Tuning" do SGBD.
- São usualmente criados para as PKs e FKs.
	- FK's são importante para os JOINS (é junção entre tabelas).
- Índices devem ser seletivos (únicos).
	- Índices que se repetem muito não devem ser utilizados para ordenação 
		- Estados - 80% dos campos são MG.
	- Colunas muito utilizadas em cláusulas WHERE também são boas candidatas para índices.
#### Unicidade 
- Os índices podem ou não ser únicos (UNIQUE).
	- O índice é único quando não se permitem repetições no conjunto de campos que compõem o índice. O índice pela PK é sempre UNIQUE.
		- Garante unicidade de valor.
	- Índices **não-únicos** permitem valores duplicados para colunas.
- Em alguns SGBD's o índice pela PK é criado automaticamente.
#### Sintaxe
- CREATE \[UNIQUE] **\[CLUSTERED | NONCLUSTERED]** INDEX
	Nome-do-Índice ON tabela (coluna ou lista de colunas)
- DROP INDEX Nome-do-Índice
	- Deleta o índice 
- Clusterização
	- Ordenação física, CLUSTERED obriga que os itens estejam fisicamente na ordem desejada.
		- Overhead na inclusão, mas busca fica mais fácil de buscar (fisicamente no computador inclusive).
```sql
-- Exemplo 1
CREATE UNIQUE INDEX CLUSTERED IX_Funcionarios ON Funcionarios (Matricula)
-- Ex. 2
CREATE INDEX IX_salario ON Funcionarios (CodDepto, Salario)
-- Ex. 3
CREATE INDEX Ind_Regional ON Clientes (Estado ASC, Cidade ASC)
-- Nesse caso o Estado é a chave primária, e Cidade a secundária.
```
#### Índice Composto
- Múltiplos índices podem existir para a mesma tabela.
- Mais de um índice usando as mesmas colunas pode ser utilizado, criando ordens diferentes de colunas.
```sql
-- ORDEM 1
CREATE INDEX empregado_ix1 
ON employee 
(departamento_id, manager_id)

-- ORDEM 2
CREATE INDEX empregado_ix2
ON employee
(manager_id, departament_id)
```
#### Visões
Relaciona-se à acessibilidade de informação.
- Visão é uma estrutura lógica que é montada dinamicamente a partir de um SELECT.
	- É uma janela para o BD.
- Através da visão, consegue-se selecionar as linhas e colunas desejadas de uma tabela ou mais tabelas e dar um nome lógico (nome da visão) para o resultado.
	- É um recorte cuidadoso e específico do BD.
- IMPORTANTE: SGBD não armazena as linhas resultantes da execução da visão.
	- A visão é construída dinamicamente, ela não é armazenada de forma redundante no BD.
###### Utilidade
- Utiliza-se das visões para armazenar os SELECT's mais frequentes dentro do próprio BD
	- É análogo a um macro.
	- Pode ser visto também como um "relatório pronto", ou um template de pesquisa.
		- Pode ter cálculos embutidos (média, mediana, moda).
- Segurança é uma vantagem, pode-se dar permissão de acesso para uma visão em vez da tabela inteira.
	- Outras camadas do sistema (aplicativos, programas, usuários finais) podem acessar a visão, simplificando a sintaxe dos comandos.
- Visões podem ser encadeadas, empilhadas (cuidado com queda em performance).
	- View da view.
- Serve para isolar a camada da aplicação de base.
	- Alterar as colunas de uma tabela não afeta as visões.

```sql
-- Toda visão tem um SELECT associado
CREATE VIEW staff AS
SELECT employee_id, last_name, job_id, manager_id, departament_id
FROM employees;

-- Remoção
DROP VIEW staff;

-- Forma genérica
CREATE VIEW nome_da_visao (apelidos para os campos, opcional) AS SELECT ...;

-- Exemplo
CREATE VIEW SalarioDepto (Depto, Media_Salarial, Numero)
AS SELECT Depto, AVG(Salario), COUNT(*)
FROM Funcionarios
GROUP BY Depto;

-- Visão encadeada(View de View)
CREATE VIEW MaioresSalarios
AS SELECT * FROM SalarioDepto -- View anterior
WHERE Media_Salarial > 8000;
```
### Vocabulário
#### Hamal
Hamal de uma empresa refere-se ao valor total que uma empresa deve aos seus credores e financiadores. É uma métrica financeira importante que indica a quantidade de capital que uma empresa tomou emprestado e ainda não pagou. O hamal pode incluir diversos tipos de dívida, como:
1. **Empréstimos bancários**: Dívidas contraídas junto a instituições financeiras.
2. **Debêntures**: Títulos de dívida emitidos pela empresa.
3. **Contas a pagar**: Dívidas com fornecedores e outras obrigações de curto prazo.
4. **Leasing**: Contratos de arrendamento financeiro.
Resumidamente, o hamal representa as obrigações financeiras que a empresa precisa quitar no futuro.