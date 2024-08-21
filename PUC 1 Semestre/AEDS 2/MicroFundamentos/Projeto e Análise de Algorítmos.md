### Somatórios 
#### P1 - Combinação de Conjuntos
- Permite combinar termos somatórios com conjuntos disjuntos em um único somatório.
#### P2 - Base de Perturbação 
- Introdução de termos adicionais em uma soma para facilitar a manipulação e obter resultados desejados. 
#### Métodos para a solução de somatórios
- Procure;
	Busca por padrões e regularidades na expressão ou problema em questão. Ao observar atentamente a soma e analisar os termos, é possível identificar estruturas recorrentes ou propriedades que auxiliam na simplificação ou resolução. **(Buscar forma mais compacta e/ou simplificada)**
- Adivinhe a resposta e prove por indução;
	Fazer suposição e depois provar que ela é verdadeira. 
	**Especialmente útil em problemas que envolvam sequências ou estruturas recursivas.**
	**Indução Matemática:**
		1 - **Passo base:** provar que a fórmula é verdadeira para o primeiro valor do somatório, substituindo N na equação pelo primeiro valor;
		2 - **Passe indutivo:** Supondo que _n>0_ e que a fórmula é válida quando substituímos _n_ por _(n−1)_. Utilizando a notação de somatório, temos: $$S_n=S_{n-1}+a_n,\;onde\;\;S_{n-1}$$ é a equação resultante da substituição de _n_ por _(n−1)_ e a_n é o n-ésimo termo da sequência.
- Perturbe a soma;
### Complexidade 
- Pode ser útil analisar uma classe de algoritmos ao invés de algum algoritmo particular.
**Exemplos:**
- Ordenação (em geral): n(log(n))
	Shell sort(?).
##### Modelo Matemático para Contar Operações
- Determinar e contar as operações relevantes;
- O custo total de um algoritmo é igual a soma do custo de suas operações;
- Deconsideramos sobrecarga de gerenciamento de memória e de E/S.
- Considerar o pior caso até segundo ordem.
- Precisamos definir a função de complexidade.