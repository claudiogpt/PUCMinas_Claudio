### Junções
- Usados em consultas SELECT que combinam linhas de duas ou mais tabelas e visões.
- TABELAS/VISÕES, especificadas na cláusula FROM.
- **Condições de Ligação:** especificadas na cláusula WHERE. 
	- Usualmente feita através do relacionamento PK -> FK. Denominada: **condição de junção**.
	- A junção é um subconjunto do **produto cartesiano**.
		- Interseção.
#### Nomes de Atributos Ambíguos
- Duas colunas podem ter o mesmo nome, desde que estejam em tabelas diferentes.
- O nome da coluna então é prefixado com o nome da tabela.
```sql
SELECT empregado.nome, departamento.nome
FROM funcionario, departamento 
WHERE funcionario.dep_id = departamento.id;
	-- Where é a restrição, condição que permite achar a interseção.
```
#### Apelidos (Alias)
- Colunas de quaisquer tabelas podem ser selecionadas durante o JOIN, pode-se utilizar apelidos (alias) para as tabelas.
	- Se um campo aparece em 2 tabelas e é selecionado, é preciso informar em qual tabela ele será exibido.
	- Apelidos  podem ser criados em qualquer consulta.
	- Apelidos "facilitam a escrita" (sintetizam) do SELECT.
```sql
SELECT F.Pnome, F.Unome
FROM funcionario F, Departamento D
WHERE D.Dnome = 'Pesquisa' AND D.Dnumero = F.Dnr;
```
#### Sintaxe (Tradicional)
```sql
-- Selecione os nomes dos dptos e de seus funcionários com os cargos, em ordem alfabética do nome do dpto e do funcionário.
SELECT nome_depto, nome, cargo
FROM Depto A, Funcionario B
WHERE A.cod_depto = B.cod_depto 
ORDER BY 1, 2;

-- Selecione a média de salários dos funcionários do depto de informática (sem considerar o gerente).
SELECT AVG(salario) as Media
FROM Depto A, Funcionario B
WHERE A.cod_depto = B.cod_depto AND nome_depto = "Informática"
AND cargo <> "gerente";

-- Selecione o somatório de salários por nome de departamento, em ordem crescente do somatório 
SELECT nome_depto, SUM(salario) as SOMA
FROM Depto A, Funcionario B
WHERE A.cod_depto = B.cod_depto
GROUP BY nome_depto
ORDER BY 2 desc;
```
#### JOIN, 3 Tabelas
```sql
-- Selecione os nomes dos deptos e de seus funcionários que tenham dependentes, em ordem alfabética do nome do depto, do funcionário e do nome do dependente.
SELECT nome_depto, nome, nome_dependente
FROM Depto A, Funcionario B, Dependente C
WHERE A.cod_depto = B.cod_depto AND B.matricula = C.matricula
ORDER BY 1, 2, 3; -- ASC(Menor para maior), default.
```
#### Tipos de Junções
- Inner Join (sintaxe tradicional).
```sql
-- INNER JOIN (INTERSEÇÃO), BOA PRÁTICA
SELECT coluna1, coluna2, ... colunaN
FROM tabela1 JOIN tabela2 ON tabela1.coluna = tabela2.coluna,
WHERE <outras_restrições>;

-- Sintaxe Alternativa
SELECT coluna1, coluna2, ... colunaN
FROM tabela1, tabela2
WHERE tabela1.coluna = tabela2.coluna;
```
- Left outer join
```sql 
-- LEFT JOIN (Inner + Esquerda)
-- Selecione o nome dos funcionários e de seus dependentes, exibindo também os funcionários sem dependentes, em ordem alfabética dos nomes
SELECT nome, nome_dependente
FROM Funcionario A LEFT JOIN Dependente B
ON A.matricula = B.matricula
ORDER BY 1, 2; -- ASC(Crescente)
	-- Nesse caso: basta funcionário para ser preenchido, dependente só quando tem.
```
- Right outer join
```sql
-- RIGHT JOIN (Inner + Direita)
-- Selecione os nomes dos funcionários e de seus dependentes, exibindo também os funcionários sem dependentes, em ordem alfabética dos nomes.
SELECT nome, nome_dependente 
FROM Dependente A RIGHT JOIN Funcionario B
ON A.matricula = B.matricula
ORDER BY 1, 2; -- A tabela resultante é igual do Left Join
```
- Full outer join
```sql
-- FULL JOIN (Total do Conjunto)
-- Selecione os nomes dos departamentos e dos funcionários exibindo departamentos sem funcionários e também funcionários sem departamentos, em ordem alfabética dos nomes.
SELECT nome_depto, nome
FROM Depto A FULL JOIN Funcionario B
ON A.cod_depto = B.cod_depto 
ORDER BY 1, 2; 
	-- Diferente do produto cartesiano (todas as permutações) não gera combinações aleatórias.
```
#### Union
- Agrega resultados de comandos SELECT. Deve existir compatibilidade de colunas e as linhas duplicadas são desprezadas.
- **UNION ALL:** não elimina tuplas duplicadas.
- Equivale à operação de união da teoria dos conjuntos. Pode atuar em tabelas diferentes (compatíveis).
```sql 
-- Selecione os nomes e estados dos funcionários de MG e do RJ, marcando os de MG com um asterisco.
SELECT nome, estado, '*'
FROM Funcionario WHERE estado = 'MG' UNION
SELECT nome, estado, ''
FROM Funcionario WHERE estado = 'RJ'

-- Selecione os funcionários recém-admitidos com uma mensagem de "Bem-Vindo" e os que completaram 5 anos anos de casa com "Parabéns".
SELECT MATRIC_TEMP, NOME, 'BEM-VINDO'
FROM ENTREVISTAS
WHERE POSICAO = 'ADM' 
UNION
SELECT MATRICULA, NOME 'PARABENS'
FROM FUNCIONARIOS
WHERE ANOS = 5
ORDER BY 2;
```