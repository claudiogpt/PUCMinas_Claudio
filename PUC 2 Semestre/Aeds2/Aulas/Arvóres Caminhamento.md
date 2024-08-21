## Tipos de Caminhamento
### Pré-ordem (Pre-order)
Neste caminhamento, o nó é processado antes de seus filhos. A ordem de processamento é:
1. Visite o nó atual.
2. Caminhe recursivamente à esquerda (subárvore esquerda).
3. Caminhe recursivamente à direita (subárvore direita).

**Utilidade:** É útil para criar uma cópia da árvore ou para obter uma prefixa expressão de uma expressão aritmética. (por que?)
### Em ordem (In-order)
Neste caminhamento, o nó é processado entre os caminhamentos de seus filhos. Isso resulta na visita dos nós da árvore em uma ordem ascendente (para árvores de busca binária). A ordem é:
1. Caminhe recursivamente à esquerda.
2. Visite o nó atual.
3. Caminhe recursivamente à direita.

**Utilidade:** Este método é comumente usado para obter os elementos de uma árvore de busca binária em ordem ascendente. (por que?)
### Pós-ordem (Post-order)
Neste caminhamento, o nó é processado após seus filhos. A ordem de processamento é:
1. Caminhe recursivamente à esquerda.
2. Caminhe recursivamente à direita.
3. Visite o nó atual.

**Utilidade:** Este caminhamento é útil para deletar a árvore, pois garante que o nó será processado somente após todos os seus filhos terem sido processados (e potencialmente deletados). (por que?)
### Exemplo Visual
Considere a árvore binária abaixo:

```
     1
   /   \
  2     3
 / \   / \
4   5 6   7
```

**Pré-ordem**: 1, 2, 4, 5, 3, 6, 7  
**Em ordem**: 4, 2, 5, 1, 6, 3, 7  
**Pós-ordem**: 4, 5, 2, 6, 7, 3, 1