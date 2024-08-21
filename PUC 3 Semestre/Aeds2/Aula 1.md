### f(n) = Complexidade de Tempo
- Número de vezes que uma operação de interesse (pesada, mais relevante) é executada.
- n -> **Tamanho da entrada** ou um valor literal.
### Contagem de Operações
#### Operações Relevantes
Em complexidade de tempo, as operações mais relevantes são aquelas que dependem do tamanho da entrada (geralmente denotado por \(n\) e afetam o desempenho do algoritmo à medida que o tamanho da entrada aumenta. As principais operações que contamos são:

1. **Acessos a elementos**: Ler ou escrever um valor em um array, lista, ou outra estrutura de dados.
2. **Comparações**: Usado em loops, condições, ou algoritmos de ordenação e pesquisa.
3. **Atribuições**: Alterações de valor de variáveis, incluindo operações aritméticas como `res *= i`.
4. **Chamadas de função**: Incluindo recursão, onde o número de chamadas pode crescer com o tamanho da entrada.
5. **Movimentações de dados**: Troca de posições de elementos em um array, inserção ou remoção de elementos em listas, etc.
6. **Operações em estruturas de dados**: Como inserções, remoções ou buscas em árvores, grafos, tabelas de hash, etc.

Essas operações são relevantes porque elas influenciam o tempo que um algoritmo levará para processar uma entrada de tamanho \(n\). **Operações constantes, que não dependem do tamanho da entrada, são geralmente ignoradas na análise assintótica de complexidade de tempo (notação Big-O), exceto quando ocorrem dentro de um loop ou são repetidas várias vezes.**
### FPAA
- Equações de Recorrência (VERIFICAR)
	- Extrair complexidade dos métodos.
### Classes de Complexidade
- f(n) = 1. Constante, número fixo de execuções independente da entrada.
- f(n) = log(n). Cresce de maneira logarítmica. Tipicamente algoritmos do tipos dividir e conquistas.
	- Tipicamente de base 2.
	- log_a(b) = x <=> a^x = b
- f(n) = n. Cresce de maneira linear (junto com o tamanho da entrada).
	- **Ex:** operações com vetores, pesquisa linear...
- f(n) = n\*log(n)
	- Dividir e conquistas, mas agrupam as soluções.
- f(n) = n^2 
	- Itens processados aos pares: **Ex:** matrizes.
	- Tipicamente for aninhado.
- f(n) = n^3 
	- Sempre que n dobra, o tempo de execução é multiplicado por 8.
	- Só funciona para problemas muito pequenos, extremamente ineficiente.
- f(n) = C^n 
	- Usualmente utilizam-se soluções de força bruta.
- f(n) = n!
	- Complexidade exponencial.

