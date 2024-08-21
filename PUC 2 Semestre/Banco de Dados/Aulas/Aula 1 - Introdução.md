## Banco de Dados
### Semi - Presencial
- **Online (CANVAS)**
	- Prof. Rodrigo Baroni
- **Presencial (Sala de Aula)**
	- Prof. Marco Paulo - marcopaulo@pucminas.br
### Ementa
- Conceitos de gerenciamento de bancos de dados.
- Arquitetura de um SGDB (Sistema Gerenciador de Banco de Dados) - Relacional (no Curso)
	- Lugar comum, maior parte das aplicações utilizam SGDBs Relacionais.
		- **Ex.** caixa (tabela - hash, valor).
- Modelo de dados.
- Modelos de bancos de dados.
- Linguagens de definição, manipulação e controle de dados.
- Normalização e projeto físico de bancos de dados.
- Segurança.
### Sistemas Transacionais 
- Se utilizam de SGDBs Relacionais na maioria das vezes (não exclusivamente)
### Relacionais
- SQL ANSI (Padrão Internacional)
	- **ORACLE:** PL/SQL
	- **MS SQL SERVER:** T-SQL
#### Não relacionais
- Quando há muita variedade nos dados, geraria muitas colunas vazias em um sistema relacional
### Sistemas Analíticos (Data - Warehouse)
- **Propósito:** Projetados para análise de dados e relatórios, suportando consultas complexas que envolvem grandes volumes de dados e agregações.
- **Modelo de Dados:** Utilizam esquemas otimizados para leitura e análise, como o modelo dimensional (esquema estrela, esquema floco de neve), que facilita consultas analíticas e operações de agregação.
- **Otimização:** Otimizados para cargas de trabalho de leitura intensiva, permitindo análises rápidas e complexas. Empregam técnicas como o processamento de colunas (columnar storage), materialização de views, e indexação especializada para melhorar o desempenho das consultas analíticas.
- **Uso:** Ideal para business intelligence (BI), relatórios, análises de tendências, e tomadas de decisão baseadas em dados históricos acumulados.
### Transacional vs Analítico
 **Resumo** Sistemas relacionais são focados em transações e operações diárias de negócios, garantindo a integridade e a consistência dos dados. Sistemas analíticos, por outro lado, são focados em análise e relatórios, permitindo insights a partir de grandes volumes de dados históricos. _Ex: Data Science vs SQLServer._
- **Esquema e Modelo de Dados:** Relacionais usam um modelo normalizado para evitar redundância e garantir integridade, enquanto analíticos tendem a usar modelos desnormalizados ou dimensionais para acelerar as consultas.
- **Otimização de Performance:** Cada sistema é otimizado para seu tipo de carga de trabalho específico – transacional ou analítico.
### Projeto de BD
Banco de Dados essencialmente é um conjunto de dados que tem alguma relação entre eles (restrição).
1. Projeto Conceitual (Imaginar, Idealizar, Projetar os Dados).
	1. Lógica do negócio, proximidade do problema.
	2. Construção do Modelo de Dados
2. Projeto Lógico/Projeto Relacional
	1. Mapear o Modelo de Dados para o Modelo Relacional
3. Projeto Físico (Implementação no SGDB)
	1. Código, construção das tabelas.
#### Integridade Referencial
- Chaves primárias e estrangeiras
### Bibliografia
- Sistemas de Banco de Dados, NAVATHE 
	- Clássico, referência aprofundada.
### Avaliações
- Atividades objetivas no AVA(Canvas) - 20 pontos
- Atividades em sala de aula - 10 pontos
- Avaliação 1 - 25 pontos
- Avaliação 2 - 25 pontos
- Trabalho Prático Final - 15 pontos
	- Sem ADA: +5 pontos
- ADA (Avaliação de Desempenho Acadêmico) - 5 pontos
	- Se tiver
- Disciplina Extensionista (Junto com TI2).