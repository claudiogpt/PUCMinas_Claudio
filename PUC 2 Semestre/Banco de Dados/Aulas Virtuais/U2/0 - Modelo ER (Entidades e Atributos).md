### Modelo de Dados
- Coleção de ferramentas conceituais para descrição dos dados, seus relacionamentos, suas restrições de consistência e semântica.
#### Modelagem de Dados
- Analisar fatos relevantes e contexto do negócio para organizar os dados  em estruturas definidas e estabelecer regras de dependência entre eles, além de produzir um modelo expresso por uma representação descritiva e gráfica.
- **Geração de modelos de dados:** Hierárquico, Rede, Relacional, Pós-Relacionais, Orientado a Objeto.
### Modelo Hierárquico (Falta N x N)
- Baseado em árvore
	- **Problema:** Limitação no Relacionamento N x N.
### Modelo de Rede (Ruim -- Complexo)
- Evolução do modelo hierárquico
- Baseado na estrutura de ponteiros
	- **Problema:** Dificuldade de implementação e utilização.
### Modelo Conceitual de Entidades - Relacionamentos
- Modelo conceitual é um modelo abstrato que descreve a estrutura de um BD.
- Define QUAIS dados podem aparecer no Banco de Dados.
	- Não define COMO esses dados serão armazenados (SGBD).
- O Modelo E-R é um tipo de Modelo Conceitual, composto por entidades e relacionamentos.
- O Modelo E-R é uma forma de representar os requisitos funcionais. 
	- Requisitos funcionais: necessidades práticas do negócio.
- O Modelo E-R possui grande capacidade de redução semântica. 
	- Facilitando a compreensão pelo usuário leigo e a validação dos dados da aplicação a ser modelada.
### Entidades
- Objetos no mundo real
	- Clientes, Funcionários, Produtos...
- Estruturas abstratas de informação
	- Nota fiscal, histórico escolar, extrato bancário, tipo de produtos...
- A Entidade é representada por um retângulo nomeado (substantivo) que designa todo um conjunto
	- Pedro e Paulo são instâncias da Entidade Cliente.
### Atributos
- Elementos de dados que identificam e descrevem Entidades.
	- Fornecedor = cod-fornecedor, nome, CNPJ, endereço, valor-faturamento.
- Dado que é associado a cada ocorrência de uma entidade ou relacionamento
- É representado por uma elipse nomeada
- **Simples:**
	- Indivisíveis
	- CPF, preço, altura.
- **Composto:**
	- Divisíveis em subpartes menores, que representam atributos mais básicos, com significados independentes e que podem formar hierarquia.
	- Telefone = Código do País + Código do Estado + Número do Telefone
#### Tipos de Atributos
- **Monovalorados**: 
	- Possuem um único valor para uma dada entidade
	- CPF, Altura, peso de uma pessoa.
- **Multi-Valorados (elipse dupla):** 
	- Múltiplos valores para uma dada entidade 
	- Telefones e Endereços de Fornecedores.
- **Derivados (elipse pontilhada)**
	- Computados a partir de outros atributos ou entidades
	- Idade do Aluno (Data de Hoje - Data Nascimento), IMC de uma pessoa, Total da Nota Fiscal (Somatório dos Itens).
#### Atributo Chave (Elipse com atributo grifado)
- Atributo cujos valores são distintos nas ocorrências da entidade
- É uma restrição de unicidade (exclusividade)
- Identificador da entidade
	- CPF, código de voo, CNPJ da Empresa
- Uma entidade pode ter mais de um atributo chave
	- CPF e número de matrícula do Aluno
- Chave Composta: quando vários atributos formam uma chave
	- Número da nota fiscal + número do item, Número da Agência + número da conta.