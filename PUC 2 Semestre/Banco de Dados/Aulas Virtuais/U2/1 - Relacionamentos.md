## Relacionamentos (Losango Nomeado)
- É uma associação entre uma ou várias entidades com determinado significado 
- Conjunto de associações entre ocorrências de entidades 
### Cardinalidade 
- Propriedade do relacionamento que expressa o número de ocorrências de uma entidade que participam do relacionamento com outra(s) entidade(s).
	- 1-1 - Técnico e Time
	- 1-N - Proprietário e Veículo(s)
	- N-1  - Veículo(s) e Proprietário
	- N-N  - Paciente(s) e Médico(s), Professo(res) e aluno(s)
### Totalidade (Obrigatoriedade)
- Propriedade que especifica se a existência de uma entidade depende do relacionamento com outra entidade.
	- Pode ser parcial (opcional) ou total (obrigatório)
	- **Ex.** Sócio e Dependente
- Fundamental consultar o usuário sobre as regras de negócio para as cardinalidades e totalidades.
![[Pasted image 20240206184808.png]]
### Relacionamentos Recursivos
- Uma ocorrência de uma entidade se relaciona com outra(s) ocorrência(s) da mesma entidade.
- Uma entidade participa mais de uma vez  em um tipo de relacionamento em **papéis** diferentes.
	- **Ex.** Uma disciplina tem um ou vários pré-requisitos de outras disciplinas, uma música pode possuir várias versões que também são músicas.