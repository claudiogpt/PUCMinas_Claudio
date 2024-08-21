---
tags:
  - programming
  - programing_languages
  - aeds
---
## Methods
Queue(FIla) - First In First Out
- Enqueue - Colocar no final
- Dequeue - Tirar do Início
Stack(Pilha) - First In Last Out
- Push - Coloca no topo
- Pop - tira do topo
Todos:
- Clears - Remove todos
- Contains - retorna se a estrutura contém um objeto
- Peek, retorna o próximo objeto a ser removido da estrutura
### Properties
- Count - Indica quantidade de elementos existentes na estrutura
-  

## Métodos(OBS)
- **Enqueue em FILA VAZIA**
	1- Primeiro está vazia (front e rear indefinidos).
	2- Setar ambos para 0, por que inicialmente estão em -1.
	**obs:** acontece para gerar consistência,  dessa forma front = rear = 0, quando tem 1 elemento, ambos -1 quando está vazia (estados diferentes).
	