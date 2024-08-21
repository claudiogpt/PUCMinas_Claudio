### Funções Agregadas
- AVG: 
	- Média aritmética.
- SUM: 
	- Soma de valores.
- MAX: 
	- Valor máximo.
- MIN: 
	- Valor mínimo.
- COUNT(\*): 
	- Contador de linhas da tabela.
- DISTINCT:
	- Elimina ocorrências repetidas de um mesmo campo.
	- Não faz sentido usar para um atributo já distinto (como PK).
- COUNT(DISTINCT atributo): 
	- Contador de linhas com ocorrências diferentes de um atributo.
- ORDER BY:
	- Crescente (ASC - Default).
	- Decrescente (DESC).
	- IF NULL: registros serão inseridos na ordem de inserção.
- GROUP BY:
	- Função de agrupamento, síntese.
	- HAVING:
		- Filtro por agrupamento.
		- "WHERE" do GroupBy.
 
```sql
-- AVG: Média
-- Calcule a média de salário dos funcionários.
SELECT AVG(Salario) AS Media -- Alias(apelido) do campo.

-- SUM: Somatório
-- Calcule o somatório dos salários do Depto 1
SELECT SUM(Salario)
FROM Funcionario
WHERE cod_depto=1;

-- MIN/MAX
SELECT MAX(Salario) AS Maior, MIN(Salario) AS Menor
FROM Funcionario WHERE cod_depto = 1;

-- COUNT(*)
SELECT COUNT(*) AS Qtde
FROM FUNCIONARIO WHERE CARGO <> 'gerente'

-- DISTINCT
SELECT DISTINCT CIDADE FROM CLIENTES
	-- Cidades distintas da tabela CLIENTES.
SELECT DISTINCT ESTADO, CIDADE FROM CLIENTES
	-- Composto, só repete se ESTADO && CIDADE forem iguais.
SELECT DISTINCT CARGO FROM FUNCIONARIO

-- COUNT(DISTINCT ATRIBUTO)
SELECT COUNT (DISTINCT CARGO) AS QtdeCargos FROM Funcionario
	-- Ex: 4 Cargos Distintos de Funcionarios

-- ORDER BY
SELECT Cod_Depto, Nome FROM Funcionario
ORDER BY Cod_Depto, Nome;

SELECT Cod_Depto, Nome FROM Funcionario ORDER BY 1, 2;

SELECT Cod_Depto, Salario, Nome FROM Funcionario ORDER BY 1 ASC, 2 DESC;
	-- ASC, DESC

-- GROUP BY
SELECT CARGO, COUNT(*) AS Qtde FROM Funcionario GROUP BY CARGO;
	-- Analista: 2, Gerente: 2, Programador: 1.
SELECT Cod_depto, SUM(Salario) AS SOMA FROM Funcionario
GROUP BY Cod_depto ORDER BY 2;
	-- Agrupa por Depto: 1, 2, 3... Ordena pela SOMA(Decrescente);

-- HAVING 
SELECT Cod_depto, COUNT(*) as Qtde FROM Funcionario
GROUP BY Cod_depto HAVING COUNT(*) > 3;
	-- Agrupamentos com contagem <= 3 não serão exibidos.
```