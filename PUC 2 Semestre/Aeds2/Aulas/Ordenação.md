## Bubble Sort
## Selection Sort
### HeapSort
- O Heapsort é um algoritmo de seleção que encontra o maior elemento em uma lista, troca-o com o último e repete o processo
	- Difere do Selection Sort ao utilizar um Heap invertido para selecionar o maior elemento de forma eficiente.
##### Heap (MinHeap ou MaxHeap)
- Árvore binária em que cada nó é menor ou igual que seus filhos, fazendo com que a raiz tenha o menor valor (ou maior valor).
- Suas folhas ocupam um ou dois níveis sendo que o penúltimo é completo e as folhas do último nível se agrupam o mais à esquerda possível.
##### Funcionamento
1. **Encontrar o Mínimo**: Percorre o array para encontrar o menor elemento.
2. **Troca**: Troca o menor elemento encontrado com o elemento na primeira posição não ordenada do array.
3. **Repetir**: Repete os passos 1 e 2 para o restante do array, excluindo os elementos já ordenados, até que todo o array esteja ordenado.
## Insertion Sort
- Ordena o array um elemento por vez (como inserções em um baralho).
	- Muito eficiente para arrays quase ordenados.
##### Pior Caso
- **Ordenado Decrescente:** cada elemento tem que ser movido para o início do Array.
- **O(n^2)** 
##### Melhor Caso
- **Ordenado Crescente:** o algoritmo percorre o array uma vez comparando os elementos para verificar sua posição.
## QuickSort
- Esta versão do QuickSort é uma implementação do algoritmo de ordenação que utiliza a estratégia de divisão e conquista para ordenar elementos de um array de forma recursiva.
- **Pivô:** a mediana sempre é o meio em todas distribuições de dados, melhor escolha.
- **Não Estável**
##### Pior Caso
- **O(n^2)**
- Quando o pivô escolhido é sempre o pior, não dividindo o problema de forma eficiente.
##### Melhor Caso
- **O(n log n)**
- Quando o pivô geralmente divide o array de forma igual.
### MergeSort
