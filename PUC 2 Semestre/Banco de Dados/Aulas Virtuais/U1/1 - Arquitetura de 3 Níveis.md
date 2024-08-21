## SGBD
- O SGBD deve prover aos usuários uma visão abstrata dos dados
- Os níveis de abstração simplificam a interação do usuário com o sistema
	- Inclusive do usuário técnico
### Nível Interno ou Físico
- Nível mais baixo, descreve COMO os dados devem ser armazenados
- Trata de alocação de espaço em disco, uso de índices para melhorar a performance
- Principal nível de atuação do DBA
### Nível Conceitual ou Lógico
- Este nível descreve QUAIS dados são armazenados no BD e quais os relacionamentos entre eles.
- Principal nível de atuação do AD
### Nível Externo ou de Visão
- Visão de cada usuário (devs ou usuários finais)
- Usuários precisam de apenas parte do BD
- Podem haver diferentes visões providas pelo sistema para um mesmo BD
	-  Subconjunto do BD total
## Independência de dados
### Física
- Quando alterações no nível físico não alteram o nível conceitual
- Alterações no nível físico são necessárias ocasionalmente para melhorar a performance 
	- A principal forma é a criação de Índices para isso
## Lógica
- Quando alterações no nível conceitual não provocam modificações no nível de visão
	- **Ex.** adição de campos em tabelas
- É mais difícil de ser alcançada do que a física (os programas são muito dependentes da estrutura lógica dos dados que manipulam)
## Etapas Usuais de um Projeto de BD
- Levantamento de Requisitos
- Projeto Comercial 
	- **MER**
- Projeto lógico
	- Modelo relacional, orientado a objetos, etc...
- Projeto Físico
	- Implementação do BD
### Projeto Conceitual
- Descreve a estrutura de informação sem se preocupar com qual SGBD a base de dados vai residir
- É feita a definição dos tipos de dados que o sistema manipula e como estes se relacionam
- **Entrada:** enunciado informal e incompleto de requisitos do usuário
- **Produto Final:** visão macro do BD, esquema conceitual
- **Participantes:** AD, Usuário Final, Desenvolvedor
### Projeto Lógico
- Detalha e descreve um modelo de dados gerado na fase anterior para uma determinada classe de SGBD (relacional, OO, hierárquico, rede).
- **Entrada:** esquema conceitual.
- **Resultado:** esquema lógico descrevendo as estruturas de representação.
- **Participantes:** AD, DBA, Desenvolvedor.
### Projeto Físico
- **Entrada:** esquema lógico
- **Resultado:** script DDL para o SGBD específico
- Define de que maneira o projeto lógico vai ser fisicamente armazenado: espaço necessário em disco, periodicidade dos backups, volume de alteração dos dados, número e perfil dos usuários que terão acesso aos dados.
- **Otimização:** identificação e melhoria dos processos críticos.
- **Participantes:** DBA, Desenvolvedor. 