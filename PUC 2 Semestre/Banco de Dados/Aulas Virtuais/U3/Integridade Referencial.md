## FK - Foreign Key (Chave Estrangeira)
- Implementação física de um relacionamento do M.E.R em um BD Relacional
	- FK é sempre um ponteiro para uma PK
- Conjunto de atributos de um esquema de relação R1 que referência a chave primária (PK) de um esquema de relação R2.
### Condições:
- FK deve possuir o mesmo tipo de dado da PK.
- Um valor de FK deve referenciar um valor válido de PK (t1\[FK] = t2\[PK]) ou pode ser nulo.
### Obs:
- Uma tabela não precisa de FK.
- Uma tabela por ter mais de uma FK.
## Restrições de Integridade
- Não podem ser violadas em operações de atualização (inclusão, exclusão e alteração ) do BD.
- **Integridade do Domínio:** o valor de um campo deve obedecer a definição de valores admitidos para a coluna.
- **Integridade de Entidade:** nenhum componente de chave primária pode ser nulo.
- **Integridade de Chave:** não são admitidos valores repetidos da chave primária.
- **Integridade Referencial:** chave estrangeira é um valor válido de chave primária (ou NULL).
### Problemas de Integridade Referencial 
- **Inclusão de Tupla:** qualquer violação provoca a rejeição de inserção.
	- **Restrição de Domínio:** valor fora do domínio (valores de tipos diferentes).
	- **Restrição de Chave:** valor já existente.
	- **Restrição de Integridade de Entidade:** chave nula.
	- **Restrição de Integridade Referencial:** chave extrangeira referencia tupla inexistente.
- **Exclusão de Tupla:** a violação pode ser bloqueada (restrict)
	- **Restrição de Integridade Referencial:** tupla é referenciada por chaves extrangeiras
- **Alteração de Tuplas:** 
	- Chaves normalmente não são atualizadas.
	- Integridade de domínio e integridade referencial precisam ser verificadas.
	- Usualmente qualquer violação provoca a rejeição da atualização, embora a alteração da chave possa ser propagada para a tupla que a referencia.
#### On Delete || On Update
- **Set NULL:** o valor da coluna afetada é mudado para NULL.
- **Set DEFAULT:** o valor da coluna afetada é mudado para o valor padrão especificado da coluna.
#### On Delete
- **Cascade:** exclui todas as linhas de referência.
#### On Update
- **Cascade:** muda o valor do atributo de FK de referência para o novo valor de PK atualizado de todas as linhas de referência.