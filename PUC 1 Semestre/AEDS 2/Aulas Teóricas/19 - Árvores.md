## Árvore Binária
- Caminhamento
	- Caminhar em Ordem (Esquerda, Raiz, Direita)
	- Pre Ordem(Raiz, Esquerda, Direita)
	- Pos Ordem(Esq, Dir, Raiz)
### Exercício Resolvido
- Método que retorna a altura da árvore
```python
# Define o Nó
class Node:
    def __init__(self, value):
        self.left = None
        self.right = None
        self.value = value

# Calcula altura da árvore
def height(node):
    # Nó vazio tem altura -1 (ou 0, conforme a definição)
    if node is None:
        return 0
    
    # Altura de um nó é 1 mais o máximo das alturas dos filhos
    left_height = height(node.left)
    right_height = height(node.right)
    
	#Retorna qual altura é maior, da esquerda ou da direita
    return 1 + max(left_height, right_height)

# Exemplo de uso
if __name__ == "__main__":
    root = Node(1)
    root.left = Node(2)
    root.right = Node(3)
    root.left.left = Node(4)
    root.left.right = Node(5)
    root.left.right.right = Node (6)
    print("Altura da árvore:", height(root))
```
- Método que retorne a soma dos elementos existentes na árvore
```python
class Node:
    def __init__(self, value):
        self.left = None
        self.right = None
        self.value = value

# Calcula a soma dos elementos da árvore
def sum_tree(node):
    # Se o nó está vazio, retorna 0 - Caso Base
    if node is None:
        return 0
    
    # Soma do valor do nó atual com as somas das subárvores esquerda e direita
    return node.value + sum_tree(node.left) + sum_tree(node.right)
    # Raiz + Filho Esq + Filho Dir (até filhos = 0)

# Exemplo de uso
if __name__ == "__main__":
    root = Node(1)
    root.left = Node(2)
    root.right = Node(3)
    root.left.left = Node(4)
    root.left.right = Node(5)
    root.left.right.right = Node(6)
    print("Soma dos elementos da árvore:", sum_tree(root))
```
- Faça um método estático que recebe dois objetos do tipo árvore binária e retorne um booleano indicando se as duas árvore são iguais
	- //Caminha pelas árvores (Utilizando o mesmo tipo de caminhamento) 
	- //Transforma as árvore binárias em vetores 
	- //Compara os vetores sequencialmente
- Solução Usando estrutura auxiliar
```python
from collections import deque

class Node:
    def __init__(self, value):
        self.left = None
        self.right = None
        self.value = value

# Converte a árvore em um vetor usando uma travessia em ordem
def tree_to_vector(root):
    stack = []
    output = []
    current = root

    while stack or current:
        if current:
            stack.append(current)
            current = current.left
        else:
            current = stack.pop()
            output.append(current.value)
            current = current.right
    
    return output

# Compara se duas árvores são iguais
def are_trees_equal(root1, root2):
    vector1 = tree_to_vector(root1)
    vector2 = tree_to_vector(root2)

    return vector1 == vector2

# Exemplo de uso
if __name__ == "__main__":
    # Construindo a primeira árvore
    root1 = Node(1)
    root1.left = Node(2)
    root1.right = Node(3)
    root1.left.left = Node(4)
    root1.left.right = Node(5)
    
    # Construindo a segunda árvore
    root2 = Node(1)
    root2.left = Node(2)
    root2.right = Node(3)
    root2.left.left = Node(4)
    root2.left.right = Node(5)
    
    # Verificando se as árvores são iguais
    result = are_trees_equal(root1, root2)
    print("As árvores são iguais:", result)
```
- Solução Recursiva
```python
class Node:
    def __init__(self, value):
        self.left = None
        self.right = None
        self.value = value

    @staticmethod
    def are_trees_equal(tree1, tree2):
        # Ambas as árvores estão vazias, são iguais
        if tree1 is None and tree2 is None:
            return True
        # Uma das árvores é vazia e a outra não, são diferentes
        if tree1 is None or tree2 is None:
            return False
        
        # Compara valor do nó atual e chama recursivamente para os filhos
        return (tree1.value == tree2.value and 
                Node.are_trees_equal(tree1.left, tree2.left) and 
                Node.are_trees_equal(tree1.right, tree2.right))
        # Tem que garantir que a passagem de valores é sempre dos mesmos locais, isso pode gerar bugs
# Exemplo de uso

if __name__ == "__main__":
    # Construindo a primeira árvore
    root1 = Node(1)
    root1.left = Node(2)
    root1.right = Node(3)
    root1.left.left = Node(4)
    root1.left.right = Node(5)
    
    # Construindo a segunda árvore
    root2 = Node(1)
    root2.left = Node(2)
    root2.right = Node(3)
    root2.left.left = Node(4)
    root2.left.right = Node(5)
    
    # Verificando se as árvores são iguais
    result = Node.are_trees_equal(root1, root2)
    print("As árvores são iguais:", result)
```
#### Exercícios Difíceis
- Escrever um algoritmo que calcula a altura de uma árvore, usando uma estrutura de dados auxiliar.
- Escrever um algoritmo que calcula a largura de uma árvore (usando uma estrutura de dados aux).
	- Largura: quantidade de nós filhos.