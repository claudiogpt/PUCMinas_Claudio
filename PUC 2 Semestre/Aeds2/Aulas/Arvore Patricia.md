### Practical Alphanumeric to Retrieve Information Coded in Alphanumeric
- Elimina nós redundantes.
	- Todos os nós (exceto raíz) tenham pelo menos dois filhos.
	- Na trie padrão, a existência de nós com apenas um filho representa ineficiência de tempo-espaço.
#### Propriedades
- Substrings: cadeias de caracteres da coleção S.
- Temos 0(s) nós - onde S é o número de cadeias da coleção.
- O número de nós é proporcional ao número de cadeias da coleção S; não ao comprimento das mesmas.
- Todo nó interno tem entre 2 e d filhos.
	- Na árvore Patrícia, cada nó interno (exceto as folhas) terá entre 2 e d filhos, onde d é a quantidade de caracteres possíveis (por exemplo, para cadeias de caracteres ASCII, d = 256). Isso garante que a árvore não se torne degenerada (ou seja, uma lista encadeada), mantendo uma estrutura balanceada que permite buscas rápidas.
### Estrutura de Dados
- Cada nó armazena uma tripla de inteiros (i, j, k), indicando o rótulo do nó
	- i -> índice da cadeia na coleção
	- j -> posição inicial da substring
	- k -> posição final da substring (inclusiva) 
- A coleção de cadeias S será S\[0], S\[1],... S\[s-1] 
	- Índice das cadeias em si.