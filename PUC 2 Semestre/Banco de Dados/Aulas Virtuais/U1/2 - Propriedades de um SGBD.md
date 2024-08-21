### **Integridade**
- Garante que os dados armazenados representam as informações do mundo real de forma precisa.
	- Sem corrupção ou perda de dados.
- **Exemplos:**
    - Um banco de dados de clientes deve ter informações precisas sobre seus nomes, endereços e números de telefone.
    - Um banco de dados de produtos deve ter informações precisas sobre os preços e quantidades em estoque.
### **Segurança**
- Garante que os dados sejam acessados por pessoal autorizado.
- **Exemplos:**
    - Os usuários devem ter que se autenticar com um nome de usuário e senha para acessar o banco de dados.
    - **Visões:** Diferentes usuários podem ter diferentes níveis de acesso aos dados, de acordo com suas necessidades.
### **Backup e Recuperação (Restore)**
- Em casos de falhas (elétrica, bugs, defeitos nos equipamentos) o SGBD deve prover instrumentos pra detectar tais falhas e restaurar o BD ao estado anterior.
	- Restauração (último Backup).
### **Concorrência**
- **Definição:** A concorrência garante que vários usuários possam acessar o banco de dados ao mesmo tempo sem que os dados sejam corrompidos. Isso é importante para sistemas multiusuários.
- **Exemplos:**
    - O SGBD deve usar mecanismos de controle de concorrência para garantir que os dados sejam acessados de forma ordenada.
    - Os usuários não devem ser capazes de sobrescrever as alterações uns dos outros.
### **Monitoramento**
- Fornece ferramentas que possibilitam a verificação de como o sistema está se comportando a cada momento.
	- Recursos muito usados pelo DBA para o tunning do BD.
- **Exemplos:**
    - O SGBD pode fornecer ferramentas para monitorar o uso da CPU, memória e disco.
    - O SGBD pode gerar alertas quando ocorrerem problemas.
	    - Passível de automações
### **Natureza Autodescritiva do Sistema de BD:**
- O sistema possui (além do BD) uma completa definição ou descrição estrutural do BD e suas restrições.
	- **Catálogo, metadados.**
### **Isolamento entre os Programas e Dados - Independência de Dados**
- **Modelo de arquivos:** 
	- Mudar a estrutura de arquivos pode exigir mudar todos os programas que o acessam (antiquado).
- **Abordagem BD:** 
	- A estrutura dos arquivos de dados é armazenada no catálogo do SGBD, separadamente do programa de acesso.
### Suporte para as Múltiplas Visões dos Dados:
- Um BD genérico possui muitos usuários, cada um necessitando diferentes visões do BD.
### Compartilhamento de Dados e o Processamento de Transações Multiusuários:
- O SGBD deve incluir um software de controle de concorrência para garantir que muitos usuários, ao tentar atualizar o mesmo dado, façam de modo controlado, para assegurar que os resultados das atualizações sejam corretos.
	- Evitar corrupção dos dados.
- Uma transação é um programa em execução ou um processo que inclui um ou mais acessos ao banco de dados:
	- **Ex.** transferência bancária.
		- Em caso de só uma das partes for executada, acontece o RollBack de forma programática.
### Controle de Acesso e Autorização
- A maioria dos usuários não é autorizada a acessar todas as informações disponíveis no BD. 
	- Privilégios de consulta e/ou atualização -- SEGURANÇA 
- SGBD deve garantir a segurança e um subsistema de autorização usado pelo DBA para criar contas e definir as restrições de cada uma ou de um grupo.
### Controle de Redundância
- Na abordagem de arquivos, cada aplicação mantém seus arquivos de maneira independente.
- Na abordagem de BD, as visões de todos os grupos são integradas durante o projeto do Banco.
### Persistência de Dados
- Armazenamento persistente de conteúdo, estruturas e regras de negócio.
### Múltiplas Interfaces para os Usuários
- Linguagens de consulta para usuários causais;
- Interface de linguagens de programação para programadores de aplicações;
- Interfaces gráficas com menus entre outras.
### Armazenamento de Estruturas para o Processamento Eficiente de Consultas:
- O módulo do SGBD para o processamento de consulta e otimização é responsável pela escolha eficiente do plano de execução da consulta (query) baseado na estrutura de armazenamento existentes (índices).
### Representação de Múltiplos Relacionamentos
- Grande variedade de dados que estão inter-relacionados de muitas maneiras
### Padronização do Ambiente
- Nome e formato do tipo de dados
### Implementação de Restrições de Integridade e Regras de Negócios
- Especificação de um tipo de dado para cada item de dados.
- Restrições semânticas como unicidade e relacionamento entre os dados.
	- **Unicidade:** garante que cada registro seja único. Exemplo: CPF em um banco de dados de clientes.
	- **Relacionamento entre os dados:** define as relações entre as tabelas. Exemplo: chave primária e chave estrangeira.
- Benefícios como redução no tempo de desenvolvimento de aplicações, economias de escala, flexibilidade.
### Conclusão:
- O SGBD facilita o desenvolvimento de novas aplicações.
- O principal objetivo de um SGBD é proporcionar um ambiente conveniente e eficiente para armazenar e recuperar informações no BD.
