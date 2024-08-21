## Find MinMax(Array)
- **Original:**
	Compara cada índice -> min ? true : false, max ? true : false
	**Complexidade** O(2n)
- **Otimizado:**
	Compara 2 indices de uma vez
	**Complexidade** O(n/2)
#### MergeSort
**Caso base:**
	-> sublista <= 1;
**Caso recursivo:**
	Dividir ao meio,
	Recursivamente ordenar as sub-listas,
	Mesclar as sub-listas ordenadas.
**Ordenação Sublistas**
	Ocorre no merge a comparação dos elementos.