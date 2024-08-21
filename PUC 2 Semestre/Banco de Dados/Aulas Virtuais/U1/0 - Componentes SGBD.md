## Arquitetura Interna
- Composto por Banco de Dados Armazenado
	- Software SGBD
	- Catálogo (metadados: informações sobre o Banco de Dados).
		- Auxilia na recuperação dos dados por meio das consultas
![[Pasted image 20240204225116.png]]
### DDL (Data Definition Language)
- Linguagem para definir, alterar ou excluir estruturas de dados (objetos).
	- `CREATE`: Cria novas tabelas, índices, ou outros objetos de banco de dados.
	- `ALTER`: Modifica a estrutura de objetos existentes, como adicionar, modificar ou excluir colunas em uma tabela existente.
	- `DROP`: Exclui objetos do banco de dados, como tabelas, índices, ou visões.
	- `TRUNCATE`: Remove todos os registros de uma tabela, mas mantém a estrutura para uso futuro.
### DML (Data Manipulation Language)
- Conjunto de comandos usados em bancos de dados para inserir, atualizar, excluir e consultar dados. Diferentemente do DDL, que lida com a estrutura do banco de dados, o DML foca nos dados dentro dessas estruturas.
	- `INSERT`: Insere dados em uma tabela.
	- `UPDATE`: Atualiza dados existentes em uma tabela.
	- `DELETE`: Exclui dados de uma tabela.
	- `SELECT`: Recupera dados de uma ou mais tabelas.
**DML Procedural:**
- Usuário precisa especificar o dado e o caminho.
- Similar a linguagens de programação comuns.
**DML Não Procedural (Facilita a gestão humana de dados):**
- Usuário só especifica o dado.
- Padrão SQL.
- Cabe ao Otimizador do SGBD definir o caminho de acesso aos dados no momento do processamento da consulta.
### Componentes Técnicos
#### Processador de Consultas
- Pré-Compilador de DML
	Responsável por analisar e otimizar instruções DML (como INSERT, UPDATE e DELETE) antes de serem compiladas. Essa etapa inclui:
	- **Análise léxica:** verifica se a sintaxe da instrução está correta.
	- **Análise sintática:** verifica se a estrutura da instrução está correta.
	- **Análise semântica:** verifica se os nomes das tabelas e colunas existem e se os valores das colunas são válidos.
	- **Otimização:** modifica a instrução para melhorar o desempenho da consulta.
- Compilador de DML
	- O compilador de DML converte a instrução DML pré-compilada em código de máquina que pode ser executado pelo SGBD.
- Interpretador de DDL
	- O interpretador de DDL (Data Definition Language) é responsável por analisar e executar instruções DDL (como CREATE TABLE e ALTER TABLE) que definem a estrutura do banco de dados.
- Mecanismo de Consultas
	O mecanismo de consultas é o componente central do processador de consultas. Ele é responsável por:
	- **Análise de consulta:** verifica se a consulta está correta e gera um plano de execução.
	- **Otimização de consulta:** busca a maneira mais eficiente de executar a consulta.
	- **Execução da consulta:** acessa o banco de dados e recupera os dados solicitados.
	- **Retorno dos resultados:** envia os dados recuperados para o cliente.
#### Sistema de Armazenamento:
- Gerenciador de Buffer
	O gerenciador de buffer, também conhecido como buffer pool, é um componente crucial do sistema de armazenamento de um SGBD. Ele atua como um cache de memória principal, armazenando páginas de dados acessadas recentemente do disco. Essa estratégia visa acelerar o acesso aos dados, reduzindo significativamente o número de leituras e gravações no disco, que são operações mais lentas.
	1. **Leitura de dados:** Quando uma consulta precisa acessar dados que não estão no buffer pool, o gerenciador de buffer os lê do disco e os armazena no buffer.
	2. **Acesso a dados:** As consultas subsequentes que acessam os mesmos dados podem encontrá-los no buffer pool, evitando a leitura do disco.
	3. **Substituição de páginas:** O buffer pool possui um tamanho limitado. Quando uma nova página precisa ser armazenada, o gerenciador de buffer decide qual página existente deve ser removida para liberar espaço. Diversos algoritmos de substituição são utilizados, como LRU (Least Recently Used) e FIFO (First In First Out).
- Gerenciador de Arquivo
	O gerenciador de arquivos é responsável por gerenciar o armazenamento físico dos dados no disco. Ele controla a alocação e desalocação de espaço em disco, organiza os dados em arquivos e fornece acesso aos dados para o SGBD.
	- **Gerenciamento de espaço em disco:** Aloca e desaloca espaço em disco para armazenar dados.
	- **Organização de dados:** Organiza os dados em arquivos e estruturas de dados eficientes para acesso rápido.
	- **Controle de acesso:** Controla o acesso aos dados por diferentes usuários e aplicativos.
	- **Proteção de dados:** Implementa medidas para proteger os dados contra perda e corrupção.
- Gerenciador de Transações
	- Se preocupa com a integridade das transações
		- **Ex.** momentos de pico, mantendo integridade durante transações concorrentes.
## Componentes Humanos
#### AD (Administrador de Dados)  
- Visão mais lógica e de modelagem: "Arquiteto".
- Define a estrutura de informação da empresa (base de dados).
- Administra a descrição da base de dados (dicionário de dados).
- Define padrões para codificação de objetos da base de dados (tabelas, nomes de campos).
- Zela pelo modelo corporativo de dados.
- Conhece mais a fundo a lógica do negócio.
#### DBA (Database Administrator)
- Visão mais física da implementação: "Engenheiro".
- Perfil de Analista de Suporte: performance, otimização, armazenamento.
- Gerencia a base de dados instalada.
- Modifica a estrutura de armazenamento e a organização física: migrações, carga de dados, atualização de versões.
- Fornece e controla as autorizações de acesso ao SGBD.
- Administra o SGBD (Sistema Gerenciador de Banco de Dados).
- Especialista no SGBD específico (Oracle, SQL Server, MySQL, PostgreSQL...).
#### Engenheiro de Software/Dev
- Coleta os requisitos e necessidades de informação dos usuários finais.
- Desenvolve os sistemas que acessam o banco de dados.
- Trabalha junto com o AD na modelagem do BD.
- Trabalha junto com o DBA na implementação do BD.
#### Usuário Final
- Acessa o banco de dados para consultas, atualizações, geração de relatórios.
- Usuário nível operacional e gerencial.