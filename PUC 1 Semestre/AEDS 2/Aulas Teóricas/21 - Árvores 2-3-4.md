## 2-3-4
- Árvores que tem 2-3-4 filhos.
- Árvore vermelha preta, jeito de implementar árvore 2-3.
### Introdução e Pesquisa
- Árvores de pesquisa cujos nós são de três tipos (2nó, 3nó, 4nó) e as folhas estão situadas no mesmo nível.
	- 2nó
		- 1 elemento, 2 nós filhos
	- 3nó
		- 2 elementos, 3 nós filhos
	- 4nó
		- 3 elementos, 4 nós filhos
#### Fragmentação na Descida
- 
#### Fragmentação por Ascenção
- Efeito Cascata de Fragmentação
	- Vai propagando até a raiz (tem complexidade de tempo e energia, muitas propagações ocorrendo)
##### Eliminação da Cascata de Fragmentações
- Pode ser obtido proibindo que a árvore tenha dois **4-nós seguidos**
### Técnicas Proativas vs Reativas
- Reativas: espera o problema acontecer e resolve
- Proativas: resolve de forma antecipada
