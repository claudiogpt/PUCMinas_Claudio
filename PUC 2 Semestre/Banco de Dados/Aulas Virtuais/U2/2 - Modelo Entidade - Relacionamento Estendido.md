# Conceitos Avançados
- Entidade Forte/Fraca
- Atributos de Relacionamento
- Relacionamentos Binários ou Ternários
- M.E.R Estendido: Generalização e Especialização
	- Similar a herança em OOP
## Entidades Fracas
- Não tem chave própria
- Instâncias são identificadas por meio do relacionamento com entidades de outro tipo (identificador), juntamente com valores de alguns atributos (chave parcial).
- Sua identidade depende da entidade forte.
**RETÂNGULO DUPLO**
## Grau de Relacionamento: Binários e Ternários
- Número de tipos de entidades participantes de um tipo de relacionamento.
- Na maioria são binários **(grau 2)**
	- **Grau 3** - associa 2 relacionamentos.
- Entidades participantes de um relacionamento atuam com um determinado papel 
### Escolha: Binário ou Ternário
- Geralmente é difícil decidir entre relacionamento de grau N e ou vários relacionamentos de graus menores.
	- Deve ser decidido baseado na semântica ou na situação particular (qual é mais intuitivo?).
- **Nome Do Relacionamento:** esquerda para a direita, cima para baixo.
- Ternário não é muito usual.
## MER Estendido: Generalização e Especialização
- **Exemplo:** 
	- Felino -> Leopardo
	- Cliente -> Cliente Vip -> Cláudio Augusto
- Entidade de subtipo **herda** todos os atributos e relacionamentos do supertipo.
- Entidade de subtipo pode possuir atributos e relacionamentos específicos.
### Generalização
- Processo de definição de tipo de uma entidade genérica (super-classe, super-tipo) a partir de um conjunto de tipos de entidade.
	- **Pessoa:** Generalização de Pessoa Física e Pessoa Jurídica
### Especialização
- Definição de um conjunto de subclasses (sub-tipos) de um tipo de entidade.
	- **Cliente Vip:** especialização de Cliente
### Restrições: Disjunção e Completude
- **Disjunção:** subtipos podem ser disjuntos ou sobrepostos
	- Cada entidade do supertipo pode pertencer no máximo a um subtipo de especialização (OU exclusivo: XOR)
		- Representado por um círculo  e um "d".
		- **Ex:** Pessoa Jurídica ou Física (em um relacionamento).
- **Completude:** a completude do supertipo em relação aos subtipos pode ser total ou parcial. Também chamada de Totalidade ou Obrigatoriedade.
	- Cada entidade do supertipo pode pertencer a mais de um subtipo (OU inclusivo - E/OU)
		- Representado por um círculo e um "o" ou um círculo e um "s" (_overlap_ ou sobreposto).
- **Parcial:** as entidades do supertipo podem não pertencer a algum subtipo.
	- Linha simples.
- **Total:** as entidades do supertipo têm que pertencer a pelo menos um subtipo.
	- Linha dupla.
- **Combinações Possíveis:**
	- Disjunto / Total
	- Disjunto / Parcial
	- Sobreposto / Total
	- Sobreposto / Parcial
## MER Estendido - Complemento Sobre Agregação
- O DER não suporta relacionamentos entre relacionamentos.
- A agregação é uma abstração por meio do qual os relacionamentos são tratados como entidades de nível superior. ![[Pasted image 20240220213750.png]]
![[Pasted image 20240220213937.png]]
- Processo utilizado para "enxergar" um relacionamento como uma entidade.