### Sistemas Transacionais

**1. ERP (Enterprise Resource Planning)**
   - **Descrição:** Sistema que integra diversas funções de uma empresa, como finanças, recursos humanos, produção, compras e vendas, em uma única plataforma.
   - **Objetivo:** Automatizar e centralizar dados e processos de negócios para aumentar a eficiência e melhorar a tomada de decisões.
   - **Exemplo:** SAP, Oracle ERP.
**2. Operação**
   - **Descrição:** Sistemas que suportam as operações diárias de uma empresa, como gestão de estoque, logística, manufatura, e cadeia de suprimentos.
   - **Objetivo:** Garantir que os processos operacionais sejam executados de forma eficiente e em conformidade com as metas organizacionais.
   - **Exemplo:** Sistemas de gestão de armazéns (WMS), sistemas de controle de produção (MES).
**3. CRM (Customer Relationship Management)**
   - **Descrição:** Sistemas que gerenciam as interações de uma empresa com seus clientes, incluindo vendas, marketing, e suporte ao cliente.
   - **Objetivo:** Melhorar a satisfação e retenção dos clientes, bem como otimizar as estratégias de vendas e marketing.
   - **Exemplo:** Salesforce, Microsoft Dynamics CRM.
**4. Financeiro**
   - **Descrição:** Sistemas que gerenciam as funções financeiras de uma empresa, como contabilidade, contas a pagar e receber, gestão de fluxo de caixa, e relatórios financeiros.
   - **Objetivo:** Garantir a precisão e conformidade das operações financeiras e fornecer insights para a gestão financeira estratégica.
   - **Exemplo:** QuickBooks, SAP Finance, Oracle Financials.
### Níveis Operacionais
- Operação
- Gerencial 
- Executivo/Estratégico
### OLTP (Online Transaction Processing)

- **Definição:** OLTP refere-se ao processamento de transações em tempo real, onde múltiplas operações curtas e rápidas são realizadas simultaneamente, geralmente relacionadas à entrada, atualização, ou exclusão de dados em bancos de dados.
  
- **Características Principais:**
  - **Alta Concurrência:** Suporta um grande número de transações simultâneas.
  - **Transações Curtas:** As operações são rápidas e geralmente afetam pequenos volumes de dados.
  - **Consistência dos Dados:** Garante que todas as transações sejam completadas corretamente ou revertidas em caso de falha.
  - **Baixa Latência:** Responde rapidamente às solicitações dos usuários.
  - **Suporte a Aplicações de Negócios:** Usado em sistemas que exigem a manipulação constante de dados, como ERPs, CRMs, e sistemas bancários.

- **Exemplos de Aplicações OLTP:**
  - **Sistemas bancários:** Processamento de transações financeiras, como depósitos e retiradas.
  - **Sistemas de reservas:** Gerenciamento de reservas de voos, hotéis, etc.
  - **E-commerce:** Processamento de pedidos, carrinhos de compras, e transações de pagamento.

- **Tecnologias Relacionadas:** Bancos de dados relacionais como MySQL, PostgreSQL, Oracle, e SQL Server são amplamente utilizados para suportar sistemas OLTP devido à sua capacidade de lidar com transações e garantir a consistência dos dados.