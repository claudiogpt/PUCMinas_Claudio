## Árvores Binárias
- Nó raiz;
- Nós internos - que não estão nas extremidades;
- Nós folha - 0 ou 1 filhos, nas extremidades;
- Níveis - secção horizontal na árvore;
- Altura - referências até o último filho;
- Sub-árvore;
- Árvore Binária de Busca (ABB, BST - Binary Search Tree);
### Heap
- Árvore Binaria Completa, com ordenação;
## Árvore Binária de Busca
- Ideal estar balanceada (minimizar o tempo de pesquisa para todos os casos);
- Melhor raiz é a mediana;
### Classe Nó - Java
```java
class No{
	int elemento;
	No esq;
	No dir;
	//Construtor Vazio
	No(int elemento){
		this(elemento, null, null);
	}
	//Construtor Parametrizado
	No(int elemento, No esq, No dir){
		this.elemento = elemento;
		this.esq = esq;
		this.dir = dir;	
	}
}
```
### Inserção - Árvore
- Se vazia => Insere elemento
	- Senão
		- Menor? (Raiz)=> chama-se recursivamente a inserção para a sub-árvore da esquerda;
		- Maior? (Raiz)= chama-se recursivamente a inserção para a subárvore da direita
		- Senão
			- Igual? (Raiz) => Não inserir um elemento repetido
### Checar
- Recursividade (teoria);