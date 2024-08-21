### ERPs (Enterprise Resource Planning)
- Representa a parte de gestão de dados na empresa.
- Possui uma base fixa e partes móveis (módulos).
	- É caracteristico dos ERPs ter forte integração entre os módulos.
- Possui base de dados ricas em termos de informação sobre as empresas.
	- Ideal de utilizar para fazer Business Inteligence (BI).
	- Dados geralmente muito confiáveis.
#### Implementação
- Feita em módulos para não parar a empresa.
- Necessário conhecer as necessidades do operador (chão de fábrica).
	- O gestor não necessariamente sabe das necessidades da operação.
### DaraWarehouse
Um Data Warehouse (DW) é um sistema de armazenamento de dados projetado para a análise e consulta de grandes volumes de dados, coletados de diferentes fontes da empresa. Ele é estruturado para suportar a tomada de decisão, fornecendo uma visão consolidada e histórica dos dados.
##### Características
- **Integração de Dados:** Reúne e organiza dados de diversas fontes, como bancos de dados transacionais, sistemas ERP, entre outros.
- **Dados Históricos:** Armazena dados por longos períodos, permitindo análises históricas e tendências.
- **Otimização para Consulta:** Projetado para realizar consultas complexas e relatórios, priorizando a rapidez na recuperação dos dados.
- **Modelagem Dimensional:** Usa técnicas de modelagem como o esquema estrela ou floco de neve, facilitando a navegação e a compreensão dos dados.
- **Separação do Ambiente Operacional:** Os dados são extraídos de sistemas operacionais, transformados e carregados no DW, sem impactar o desempenho das operações diárias da empresa.
#### PUC
- O DW da PUC é uma junção de vários DMs (DataMarts)
	- Um Data Mart é uma subdivisão de um Data Warehouse que se concentra em um departamento ou área específica da empresa, como vendas, marketing, ou finanças. Ele contém um subconjunto de dados que é relevante para um grupo específico de usuários, permitindo uma análise mais rápida e focada.
### ODS (Operational Data Store)
ODS (Operational Data Store) é um sistema de armazenamento de dados usado para consolidar e integrar dados de diversas fontes operacionais de uma empresa. É projetado para suportar operações do dia a dia e fornecer uma visão centralizada e atualizada dos dados.
- Stage dos dados (brutos) para serem processados.
### Características principais:
1. **Integração de Dados**: O ODS coleta dados de múltiplas fontes, como sistemas de ERP, CRM, e outros sistemas operacionais.
2. **Dados Atualizados**: Os dados no ODS são frequentemente atualizados para refletir as operações em tempo quase real, ao contrário de um data WareHouse que pode ser atualizado com menor frequência.
3. **Suporte a Operações**: Ele é usado para tarefas operacionais, como relatórios diários ou análises de curto prazo.
4. **Menor Granularidade**: Comparado a um data WareHouse, o ODS normalmente mantém dados detalhados em vez de agregados.
### Business Intelligence
- Utiliza o Modelo Dimensional (ou Multidimensional)
#### Ferramentas de BI
- Decididas a partir da infraestrutura do parceiro.
- Geralmente utiliza-se mais de uma ferramenta para o mesmo trabalho.
#### Aeds2
- Árvore B* - Árvore utilizada para ordenação em Banco de Dados (Processamento da Consulta).
	- Verificar no ChatGPT.