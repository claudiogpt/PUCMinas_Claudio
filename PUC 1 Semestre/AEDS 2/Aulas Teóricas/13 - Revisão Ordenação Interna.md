### Elementares
##### Selection Sort
- Selecionar iterativamente o menor elemento não ordenado e colocá-lo em sua posição final
**Comparações**
- Melhor caso: Omega(n^2).
- Pior caso: O(n^2)
##### Insertion Sort
- Inserir primeiro elemento da parte não ordenada do array, deslocando elementos se necessário.
**Comparações**
- Melhor caso: Omega(n)
- Pior caso: O(n^2)
- **-> Shell Sort**
### Robustos
##### Merge Sort
- dividir o array recursivamente na metade e reconstruir o array usando mesclagem (até 1 elemento)
**Comparações**
- Melhor caso: Omega(n log n)
- Pior caso: O(n log n)
- Lembrar que normalmente usa muita memória auxiliar
##### Quick Sort
- escolhe-se um elemento como pivô, reorganiza-se menores elementos à esquerda, maiores à direita
**Comparações**
- Melhor caso: Omega(n log n)
- Pior caso: O(n^2)
##### Heap Sort
- constrói-se uma heap binária, retira-se elemento por elemento da heap até ficar vazia
	- pilha e fila -> tipo de heap
**Comparações**
- Melhor caso: Omega(n log n)
- Pior caso: O(n log n)
### Ordenação Inteiro
##### Count Sort
**Comparações**
- Melhor caso: Omega(n)
- Pior caso: O(n)
- **-> Radix Sort**

-------------------------------------------------------------------------------
### Heap
- Estrutura de Dados Especializada

-------------------------------------------------------------------------------
## Ordenação Parcial
- Utilizado em mecanismos de busca 
#### Seleção Parcial
- Selecionamos apenas os **k menores**.
- (Comparações) Praticamente Linear (Depende do tamanho de k).
#### Inserção Parcial
- Poderá gerar perda de elementos previamente selecionados.
- (Comparações) Depende de k, praticamente linear.
#### QuickSort Parcial
- Enquanto i < k (diferenciação)
#### HeapSort Parcial
- **Primeira Etapa:** Construa o heap invertido usando apenas com os k primeiros elementos.
	- Se > k -> Descarta
- **Segunda:** ordena comparativamente os descartados e os arr k.
**Pergunta:** por que o heapsort começa em 2?
