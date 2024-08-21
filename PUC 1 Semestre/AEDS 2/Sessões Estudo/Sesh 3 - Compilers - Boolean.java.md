---
tags:
  - programming
  - oop
  - programing_languages
  - c
---
**Compiler Time:**
- When I know what do I need when coding;
**Runtime:**
- When the information I need comes when running the program;
### Malloc vs Calloc
-  Funções em C para alocar memória dinamicamente, a diferença entre elas está na forma em que inicializam a memória alocada.
- **Malloc (Memory Allocation)** - aloca um bloco de memória mas não inicializa. Os valores na memória alocada podem ser desconhecidos e não nulos. O programmador precisa definir manualmente os valores desejados.
	**Exemplo:**
```c
int *array = (int *) malloc(5 * sizeof(int)); // Aloca espaço para 5 inteiros
if (array != NULL) {
    // Você deve definir os valores manualmente
    for (int i = 0; i < 5; i++) {
        array[i] = 0; // Inicializa com zero, por exemplo
    }
}
// *array -> ponteiro para o array
// (int *) -> conversão do  array para um ponteiro de inteiros
```
- **Calloc (Contiguous Allocation)** - Aloca um bloco de memória com todos os bytes inicializados para 0. É útil para garantir que a memória alocada esteja limpa.
	Exemplo:
```c
int *array = (int *) calloc(5, sizeof(int)); // Aloca e inicializa espaço para 5 inteiros
if (array != NULL) {
    // A memória já está inicializada com zeros
}
```
