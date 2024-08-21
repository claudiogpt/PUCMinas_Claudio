- Baseado na teoria dos Conjuntos.
	- Surgiu conceitualmente, foi implementado na IBM em 74 (protótipo).
- Modelo Relacional: Teoria.
	- SGBDs - Implementação específica com nuances e otimizações.
	- Banco de Dados como conjuntos de relações (tabelas).
## Relação: Partes e Propriedades
- Tabela de valores, cada linha representa uma coleção de dados relacionados.
- **Tuplas:** linhas de uma relação precisam ser distintas, as tuplas de uma relação não são ordenadas.
	- Visualizadas como linhas em uma tabela, onde cada coluna representa um atributo e cada célula contém um valor correspondente àquele atributo para uma determinada tupla. Elas são essenciais para representar os dados de maneira organizada e estruturada em um banco de dados relacional.
		- {**Idade:** 10, **Nome:** Cláudio, **Sexo:** Maculino}
- **Atributo:** cabeçalho de cada coluna. O número de atributos define o grau da relação.
	- Os valores dos atributos são **atômicos**, sem grupos repetitivos.
	- Os atributos podem ter valores **nulos**, sendo que nulo significa _inexistência de valor_(diferente de 0).
### Atomicidade
- Modelo Relacional não implementa valores multivalorados (quebraria a atomicidade: só um valor para uma coordenada linha x coluna).