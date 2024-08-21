**HeapSort** -> Ordenação com uma Estrutura de Dados.
- **Heap**
	Árvore Binária
	**Propriedade Recursiva**
	- O elemento pai é sempre o menor, recursivamente.
**Exemplo:**
	Ordenar 'S','O','F','T','W','A','R','E'.

#### Fila de Prioridades
- Estrutura de dados abstrata
- Suporta a menor remoção (ou maior) elemento
- Desempenho depende da implementação

**Implementações**
- Como eu implemento cada tipo de operação para necessidades diferentes.
	- Arranjo Desordenado
	- Arranjo Ordenado
	- Heap Binária
	**Pós-Graduação:**
	- Heap d-ária
	- Heap de Fibonacci
**API - Application Programming Interface**
- Interface -> Inserir, Remover-Menor, Recuperar

### Fila de Prioridades - Aplicações
"80% dos problemas de computação se resolvem com Fila de Prioridades"
- Sistemas Operacionais
	- Balanceamento de Carga
	- Escalonamento de Processos
- Roteamento em Grafos
	- Algoritmo de Dijkstra
		- Aplica uma fila de prioridades, pesos.
	- Algoritmo de Prim
- Compressão de Dados
	- Algoritmo de Huffman
- Problemas de Otimização
	- Problema da Mochila
### Heap Binária
- Árvore Binária, Completa, que Segue uma Ordenação Heap
	- **Árvore Binária:** Todo nó tem zero, um ou dois nós filhos.
		- Árvore Binária != Heap Binária  -> Menor ou maior elemento é recursivamente a raiz.
	- **Árvore Completa:** Todos os níveis cheios (exceto último).
	- **Ordenação Heap:** Nó pai armazena o menor (ou maior) elemento.
#### Propriedades
- **Representação por Arranjo**
	- Elemento 1 é o menor (ou maior) elemento de todos
	- O nó pai de um nó **k** está na posição **k/2**
	- Os nós filhos de um nó **k** estão nas posições **2k** e **2k + 1**.
#### Operações
##### Inserir
- Inserir elemento no último nível mais à esquerda.
- Corrigir a propriedade de ordenação heap (promover)
```c
void inserir(struct FilaPrioridades *f, tipo_t x) {
	f->elementos[++f->tamanho] = x;
	promover(f, f->tamanho);
}

void promover(struct FilaPrioridades *f, int k){
	while ((k > 1) && (f->elementos[k] < f->elementos[k/2])){
		trocar(&f->elementos[k], &f->elementos[k/2]);
		k = k/2;	
	}
}
```
#### Heapsort - Discussão
- **Qual a complexidade computacional?**
	- Tempo O(n log n) -> remover menor elemento n vezes
	- Espaço O(n) -> espaço auxiliar para heap binária
- **É  possível sem Vec\<aux>?**
	- Basta construir a heap binária no vetor de entrada, de baixo para cima.
- **Heapsort é estável?**
	- Não!
- **Problema?**
	- Não faz bom uso da memória cache.
**Robert Sedwick** - Coursera AEDS2