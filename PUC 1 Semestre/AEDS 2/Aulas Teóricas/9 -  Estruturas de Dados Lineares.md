- **Pilha:** Primeiro a Entrar, Último a Sair (Last In, First Out - LIFO).
	Pilha de Livros
- **Fila:** Primeiro a Entrar, Primeiro a Sair (First In, First Out).
	Fila do Pão.
- **Lista:** Acesso Aleatório e Todos os Elementos.
	Lista de Tarefas

**Tipos:**
- **Estática**
	implementado com vetores, sem alocação dinâmica.
		Garantias de desempenho (no mundo real)
		Controle dos Requisitos de Memória
		Menos bugs (vazamento de recursos)
- **Flexível** 
	Usa alocação de memória (ponteiros)
		Usado no caso genérico (não conhecemos a carga de alocação)

**OBS:** Checar fila circular.
## Algoritmos de Seleção
#### Ordenação por Seleção O(n^2)
- Seleciona o menor e coloca na primeira posição.
#### Ordenação por Inserção
- Dividir o vetor "logicamente" em 2 (ordenado e não ordenado).
- Considerar elemento mais à esquerda da parte não ordenada e inserir nele na parte ordenada
	-> Realizando um Deslocamento.
- Estável
**Utilidade:**
	Algoritmo utilizado de forma auxiliar para **Arrays Quase Ordenados**
		1. Tem complexidade O(N) no melhor caso.
			1. Esse é o melhor caso dele no caso.
		2. Minimiza trocas e comparações ao identificar rapidamente elementos já ordenados.
#### Shell Sort
- Ordenação usando a distância de uma carta para outra (Insertion Sort). De forma genérica, escolher distâncias mais apropriadas para otimizar.
- Divide em subarrays de distância fixa, ordena para eles (dist H) e finaliza com insertion sort (H = 1).
**Desvantagens**
- Tempo de execução é sensível à ordem inicial do arquivo.
- Não estável.
**Vantagens**
- In-Place
- Não é ótimo, mas é eficaz
- Serve como etapa intermediária em algoritmos mais complexos
**Implementação**
```python
def shell_sort(arr):
    n = len(arr)
    gap = n // 2  # Inicializa o gap
    
    # Loop principal para reduzir o gap
    while gap > 0:
        
        # Inicia a ordenação por inserção com o gap atual
        for i in range(gap, n):
            temp = arr[i]  # Armazena o valor atual
            j = i
            
            # Compara e troca os elementos
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]
                j -= gap
            
            arr[j] = temp  # Insere o valor na posição correta
        
        gap //= 2  # Reduz o gap pela metade

# Teste do algoritmo
arr = [12, 34, 54, 2, 3]
print("Array original:", arr)
shell_sort(arr)
print("Array ordenado:", arr)
```