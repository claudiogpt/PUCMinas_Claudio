### Parceiros BI
- Fundação Torino
- Colégio Santo Antônio
- Parceiros de Colegas
### Etapas do Projeto
#### E1: Escopo e Grupos/Equipes
- Temáticas/Demanda do Parceiro
#### E2: Diagnóstico da Situação Problema
- Levantamento de Requisitos
	- Sempre pesquisar para ter conhecimento anterior ao projeto.
- Desenvolvimento Ágil (Scrum)
	- 2 Semanas/Média.
	- Prototypar na Validação
		- Nos faz ganhar tempo.
#### E3: Arquitetura
- Infraestrutura
- Orçamento
#### E4: Modelo de Dados
- Esquema Estrela 
	- Neste modelo, uma tabela de fatos central é diretamente conectada a várias tabelas dimensionais, formando uma estrutura semelhante a uma estrela.
	- **Estrutura**:
		- **Tabela de Fatos**: Contém dados quantitativos e métricas de interesse (ex: vendas, lucros). As chaves estrangeiras conectam essa tabela às tabelas dimensionais.
		- **Tabelas Dimensionais**: Armazenam atributos descritivos relacionados às dimensões dos dados (ex: tempo, produto, localização).
	- **Vantagens**:
		- **Simplicidade**: Estrutura simples, fácil de entender e navegar.
		- **Desempenho**: Consultas são rápidas devido ao menor número de junções (joins) entre tabelas.
- Esquema SnowFlake
	- O esquema floco de neve é uma extensão do esquema estrela onde as tabelas dimensionais são normalizadas, resultando em uma estrutura mais complexa e em várias tabelas ligadas entre si.
	- **Estrutura**:
		- **Tabela de Fatos**: Igual ao esquema estrela, contém dados quantitativos.
		- **Tabelas Dimensionais**: Mais normalizadas, divididas em várias tabelas menores, com relacionamentos entre elas.
	- **Vantagens**:
		- **Economia de Espaço**: A normalização elimina redundâncias de dados.
		- **Maior Flexibilidade**: Fácil de ajustar e modificar as dimensões.
	- **Desvantagens**:
		- **Complexidade**: Estrutura mais complexa e pode exigir mais junções nas consultas, o que pode impactar o desempenho.
#### E5: Integração (ETL/ELT)
#### E6: Visualização de Dados (OLAP) - Online Analytical Processing
- Estratégias
- Teoria das Cores
- Storytelling