## SQL - DML
### DML (Data Manipulation Language)
- 4 operações básicas.
	- INSERT, SELECT, UPDATE e DELETE
- Uso muito mais frequente que DDL (Data Definition Language).
	- Até mesmo usuários experientes costumam usar.
	- Uso embutido em aplicações ou via janelas de acesso ao BD.
### Sintaxe
##### Operadores 
- COMPARAÇÃO =, <>, >, <, <=, >=.
- LÓGICOS AND, OR, NOT.
- BETWEEN \<expressao1> AND \<expressao2>: testa intervalo.
```sql
-- BETWEEN: intervalo fechado.
SELECT *
FROM FUNCIONARIOS
WHERE SALARIO BETWEEN 1800 AND 2000
-- Mais expressivo(legível, sentético) que:
SELECT *
FROM FUNCIONARIOS
WHERE SALARIO >= 1800 AND SALARIO <= 2000

-- Outro exemplo:
-- Selecione funcionários que ganham entre 2000 e 3500 no departamento de informática
SELECT nome, salario -- Colunas exibidas
FROM Funcionario
WHERE salario BETWEEN 2000 AND 3500 AND cod_depto = 1 -- Dpto Informática
```
- IN (\<lista de valores>): testa presença na lista.
```sql
-- IN: verifica se um elemento pertence a um conjunto. Utilizado para substituir grandes expressões de OR para o mesmo campo.
SELECT *
FROM Funcionario
WHERE cod_depto IN(1,2);
-- Mais expressivo(legível, sintético) que:
SELECT *
FROM Funcionario
WHERE cod_depto=1 OR cod_depto=2;

-- Outro exemplo:
-- Selecione os funcionarios cujo o cargo é gerente ou contador
SELECT nome, cargo
FROM Funcionario
WHERE cargo IN("gerente","contador");
```
- IS NULL, IS NOT NULL: testa nulo.
```sql
-- IS NULL/ IS NOT NULL
-- Selecione os funcionarios cujo estado ou cidade é nula
SELECT nome
FROM Funcionario
WHERE estado IS NULL OR cidade IS NULL
```
- LIKE: testa conteúdo da string de caracteres.
	- Utilizado quando se deseja obter colunas de um registro que sigam um determinado padrão pré-especificado.
		- Ex: nomes de todos os funcionários cujo nome começa com João ou termina com Silva.
		- O caractere '%' dentro da expressão LIKE tem a mesma função do caractere '\*' no Windows, assim como o \_(underscore) tem semelhança com o '?' do Windows.
```sql
-- LIKE
SELECT nome
FROM Funcionarios 
WHERE nome LIKE "JOAO%"; -- Regex?

-- Exemplo 2:
SELECT *
FROM Funcionarios
WHERE nome LIKE "__R%" -- A terceira letra do nome do funcionário deve ser 'R'

-- Exemplo 3:
-- Selecione os funcionários cujo nome tenha o char 'u' como segundo caractere.
SELECT nome
FROM Funcionario
WHERE nome LIKE "_u%"; -- Char 'u' como segundo caractere
```
##### INSERT
- Atributos devem ser inseridos na mesma ordem da criação da tabela.
- Regras de integridade são observadas (se der errado da rollback).
	- São observados campos NULL ou DEFAULT
 
```sql 
-- Inserção Unitária
INSERT INTO <tabela>
(<lista_de_colunas>) -- OPCIONAL
VALUES (<lista_de_valores>) -- OBRIGATÓRIO

-- Inserção em Massa
-- Menos utilizado: inserir dados em nova tabela a partir de SELECT.
INSERT INTO <tabela1>
(<lista_de_colunas>)
SELECT ...;
```
##### SELECT
- Não-procedural.
- Filtros de linhas e/ou colunas.
```sql
-- Sintaxe:
SELECT <lista_de_atributos>
FROM <nome_das_tabelas>
[WHERE <condicao_de_pesquisa/filtro>];
-- Na expressão WHERE, especificam-se as condições para seleção de linhas da tabela. Qualquer expressão lógica envolvendo os campos das tabelas é válida.
-- Os campos da expressão WHERE não precisam ter sido selecionados (SELECT).

-- Exemplos:
-- Matrícula e nome dos funcionários com comissão < 150.
SELECT matricula, nome
FROM Funcionario
WHERE comissao < 150;

-- Todas as informações de todos os funcionários.
SELECT *
FROM Funcionario;

-- Selecione funcionarios de MG ou RJ que ganham uma comissão maior ou igual 100 reais.
SELECT nome
FROM Funcionario
WHERE (estado="MG" OR "RJ") AND comissao >= 100;
```
##### UPDATE
- Dica 1: 
	- Para grandes atualizações, faça o SELECT antes do UPDATE para visualizar os registros.
- Dica 2:
	- Para atualizar um único registro, informe a chave primária no filtro WHERE.
```sql
-- Sintaxe:
UPDATE <tabela>
SET <coluna1> = <expressão1>,
<coluna2> = <expressão2>, 
<coluna3> = <expressão3>,
WHERE <condição_de_alteração>; -- Filtra os registros que deseja alterar.
```
##### DELETE
```sql
-- Sintaxe
DELETE FROM <tabela>
WHERE <condição_de_exclusão>; -- Opcional mas usual.
```
##### Exemplos Gerais
```sql
-- INSERT
INSERT INTO Funcionario
(matricula, nome, cargo, salario, cod_depto)
VALUES (70, "Abel", "Analista", 2000, 1);

-- INSERT:  Mais sucinto, necessário obedecer a ordem das inclusões
INSERT INTO Funcionario
VALUES (80, "Dora", "Analista", 2500, 1, 250, "RJ", "RIO");

-- INSERT/SELECT: primeiro roda o SELECT depois insere (inserção em massa)
INSERT INTO Funcionario_TI
SELECT * 
FROM Funcionario
WHERE cod_depto=1;

-- UPDATE: Aumento de 10% para contadores
UPDATE Funcionario
SET salario=salario * 1.1 -- 
WHERE cargo="contador";

-- UPDATE: Atualização de prog. para desenvolvedor e setando salário
UPDATE Funcionario
SET cargo="desenvolvedor", salario=1800
WHERE cargo="prog";

-- DELETE
DELETE FROM Funcionario
WHERE cargo="contador";
```
- Update costuma ser restrito, especialmente em produção para evitar problemas graves.