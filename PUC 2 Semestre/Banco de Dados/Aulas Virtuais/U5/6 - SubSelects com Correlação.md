### SubSelect com Correlação
- Caso complexo em que existe ligação (correlação) de colunas do SELECT mais externo com o SELECT mais interno.
- O SELECT interno depende do externo para ser executado.
- O SELECT externo seleciona um registro e o SELECT interno é executado.
- O SELECT externo seleciona o próximo registro e o SELECT interno é executado novamente. Isso se repete até o SELECT externo chegar ao fim do registro.
#### Com Correlação vs Sem Correlação
- Quando a condição na cláusula WHERE de uma consulta aninhada referencia algum atributo de uma relação declarada na consulta externa, as duas consultas são consideradas correlacionadas.
- A consulta aninhada é avaliada uma vez para cada linha na consulta externa.
	- Muito usado na comparação de elementos em relação ao seu grupo.
	- Evita comparações distorcidas
	- Usualmente é mais caro em termos de performance, mas em determinados casos é a única solução possível.
```sql
SELECT PNome, dnr
FROM funcionario F
WHERE salario > (SELECT AVG(SALARIO)
				 FROM funcionario
				 WHERE dnr = F.dnr) -- FUNCIONA como "for" aninhado

-- RETORNO:
-- Retorna os funcionários que possuem salário maior que a media dos salarios do seu departamento.

-- EXECUÇÃO:
-- Pega a linha candidata
-- Executa a consulta interna usando o valor da linha candidata
-- Usa o valor da consulta interna para validar ou desqualificar a linha quandidata.
-- Repetir enquanto houver linhas candidatas

-- EXEMPLOS:
-- Selecione os nomes dos funcionários que ganham mais do que a média do seu respectivo departamento.
SELECT nome, salario, cod_depto
FROM Funcionario A
WHERE salario > (SELECT AVG(salario)
				 FROM Funcionario B
				 WHERE A.cod_depto = B.cod_depto);

-- Selcione os nomes dos funcionários que ganham o maior salário do seu respectivo departamento
SELECT nome, salario, cod_depto
FROM Funcionario A
WHERE salario = (SELECT MAX(salario)
				 FROM Funcionario B
				 WHERE A.cod_depto = B.cod_depto)
```
### EXISTS e NOT EXISTS
- Usados para verificar se o resultado de uma consulta aninhada correlacionada é vazio (não contém tuplas).
##### EXISTS
- TRUE: consulta aninhada retorna pelo menos uma tupla.
- FALSE: consulta aninhada não retorna tuplas.
**Sobre:**
- Testa a existência de linhas que resultariam do subselect. 
	- Pode ser substituído pelo IN.
- Exige SubSelect com Correlação, pois testa a existência da linha inteira no SubSelect.
- Os campos selecionados no SELECT interno não são tão relevantes quando se usa EXISTS.
- Usado para verificar se elementos do mesmo tipo pertencem ou não a conjuntos distintos.
```sql
-- Selecione os distintos estados que existem entre os funcionários do depto de Informática e também existem no depto de Contabilidade
SELECT DISTINCT estado
FROM Funcionario A, Depto B 
WHERE A.cod_depto = B.cod_depto AND nome_depto = 'Informatica'
AND EXISTS (SELECT DISTINCT estado 
		    FROM Funcionario C, Depto D
		    WHERE C.cod_depto = D.cod_depto AND nome_depto = 'Contabilidade'
		    AND C.Estado = A.Estado)
```
##### NOT EXISTS
- TRUE: consulta aninhada não retorna tuplas.
- FALSE: consulta aninhada retorna 1 ou mais tuplas.
```sql
-- Selecione os distintos cargos que existem no departamento 1, mas não existem no depto 2.
SELECT DISTINCT cargo
FROM Funcionario A
WHERE cod_depto = 1 AND NOT EXISTS (SELECT DISTINCT cargo
								    FROM Funcionario B
								    WHERE cod_depto = 2
								    AND A.cargo = B.cargo)
-- ALTERNATIVA:
SELECT DISTINCT cargo
FROM Funcionario A
WHERE cod_depto = 1 
AND cargo NOT IN (SELECT DISTINCT cargo 
				  FROM Funcionario B
				  WHERE cod_depto = 2);
```
### ANY e IN
- Ambos são parecidos, diferenciação sintática.
```sql
-- Selecione os nomes dos departamentos que têm funcionários que trabalham no estado de MG
SELECT nome_depto
FROM Depto 
WHERE cod_depto IN (SELECT cod_depto 
				    FROM Funcionario
				    WHERE estado = 'MG')
-- ALTERNATIVA:
SELECT nome_depto 
FROM Depto 
WHERE cod_depto = ANY (SELECT cod_depto
					   FROM Funcionario
					   WHERE estado = 'MG')
```
- Existem situações que diferenciam, como usando operadores lógicos (>, <, >=).
```sql
-- Selecione os nomes dos funcionários do depto 2 que ganham um salário maior do que qualquer funcionário do depto 1.
SELECT nome, salario
FROM Funcionario
WHERE cod_depto = 2
AND salario > ANY(SELECT salario
				  FROM Funcionario
				  WHERE cod_depto = 1)
				-- Nesse caso o ANY não pode ser trocado por IN.
```
### ALL
- Compara um elemento contra todos do seu conjunto.
- Pode ser usado em substituição ao MAX em consultas analíticas.
- Em consultas sintéticas (GROUP BY), usa-se quando se quer obter o maior ou o menor de todos.
	- Não se aplica MAX(sum(salario)) ou MAX(COUNT(\*)).
```sql 
-- Qual o depto com a maior média salarial entre todos os deptos
SELECT DEPTO, AVG(SALARIO)
FROM FUNCIONARIOS
GROUP BY DEPTO 
HAVING AVG(SALARIO) >= ALL(SELECT AVG(SALARIO)
						    FROM FUNCIONARIOS
						    GROUP BY DEPTO)

-- Selecione o nome do funcionário que tem o maior salário dentre todos os funcionários.
SELECT nome, salario
FROM Funcionario
WHERE salario >= ALL(SELECT salario FROM Funcionario)
-- ALTERNATIVA:
SELECT nome, salario
FROM Funcionario
WHERE salario = (SELECT MAX(salario) FROM Funcionario)

-- Selecione o código de departamento que têm o maior número de funcionários
SELECT cod_depto 
```
