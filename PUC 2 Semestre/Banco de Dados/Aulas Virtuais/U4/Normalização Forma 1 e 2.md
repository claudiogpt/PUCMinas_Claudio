- Conjunto de testes conduzidos no modelo para deixá-lo mais robusto (menos suscetível a anomalias) e menos redundante. Diminuir a complexidade do sistema.
## 1 Forma Normal (1FN)
- Testes normais devem ser feitos em cada esquema da relação, de forma que o BD relacional possa ser normalizado no grau desejado.
- Um esquema de relação R (tabela) está na forma 1FN se todos seus atributos forem atômicos.
	- Impedimento na criação de atributos multivalorados ou grupos redundantes.
- Cada tupla (linha) tem um identificador único (chave primária).
- As linhas são todas distintas entre si, não havendo chave primária repetida.
### Dependência Funcional(DF)
- A dependência funcional entre dois atributos (ou conjuntos de atributos) X e Y de um esquema de relação R, denotada por X -> Y, é uma restrição de integridade.
	- Estabelece que:  
		- Para tuplas t1 e t2 de uma instância R(tabela): t1\[X] = t2\[X], t1\[Y] = t2\[Y].
		- Conhecendo X sabemos o Y associado.
		- Y é funcionalmente dependente de X, X determina Y.
			- Ex: CPF -> Nome; Núm_Matrícula - > Nome_Aluno.
## 2 Forma Normal(2FN)
- Aplica-se quando a PK é composta.
- Se uma relação atende a 1FN e sua PK é simples (!composta):
	- Já atende à 2FN.
- A 2FN analisa se um atributo possui **dependência parcial** da PK:
	- Uma relação atende à 2FN se atender a 1FN e não contiver dependências parciais.
	- Se o esquema de relação R(tabela) estiver na 2FN e se todo atributo de R não pertencente a uma de suas chaves for totalmente dependente da chave primária.
### Dependência Parcial
- Gera anomalias na inserção.
	- Ocorrem quando não é possível adicionar dados a uma tabela sem depender de outras informações ou sem adicionar dados redundantes.
## 3 Forma Normal(3FN)
- Se uma relação atende à 2FN e nenhum atributo de R não pertencente a uma de suas chaves for **transitivamente dependente** da PK.
- Todos os atributos que não pertencem à chave primária dependem exclusivamente da chave primária.
- **Teste:**
	- Examinar atributos não-chave, questionando se eles depende exclusivamente das chaves.
### Dependência Transitiva
- Quando uma coluna depende de outra coluna ou conjunto de colunas que não é uma PK.
	- PK -> Chave_secundaria -> Atributo
- **Solução:** dividir a tabela maior em tabelas menores.
## Resumo
- Normalização é um processo em que normalmente se decompõe ou aumentam as tabelas para que cada uma tenha um único índice(PK).
	- Normalmente se diz que elas estão normalizadas quando se atinge a 3FN.
## BCNF - Forma Normal de Boyce-Codd 
- Versão mais rígida da 3FN.
- Especialização da 3FN.
- Trata de situações em que uma tabela tem chaves candidatas múltiplas compostas e com, pelo menos, um atributo comum, ocasionando dependência funcional.
- Relação R atende à BCNF se atender à 3FN sempre que uma **dependência funcional não-trivial** X -> A se mantiver em R, assim X é uma superchave de R.
### Dependência Funcional Trivial/Não-Trivial
- Uma dependência funcional é trivial se o lado direito da expressão é um subconjunto do lado esquerdo.
	- Ex: {Num_Matricula, Nome_Aluno} -> Num_Matricula
