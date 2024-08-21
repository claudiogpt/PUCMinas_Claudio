## Ordenação
- Quase toda aplicação requer dados de forma ordenada;
- Entrada: array com N elementos;
- Ordenação Externa e Interna;
### Análise dos Algoritmos de Ordenação Interna
- **Operações fundamentais:** comparação e movimentação entre elementos do array.
- O limite inferior em termos do número de comparações (entre elementos do array) para a ordenação interna é O(n x lg(n)) (falando de objetos genéricos).
	Vários algoritmos alcançam esse limite.

**Algoritmos Estáveis vs. Não Estáveis**
- **Algoritmo estável:** depois da execução, os elementos com a mesma chave mantiveram a ordem relativa entre as chaves repetidas.
	Mesma chave == mesmo atributo.
	- A próxima ordenação não avacalha a anterior
- **Algoritmo instável:** a segunda ordenação interfere na primeira.

**Funcionamento Básico** - SelectionSort
- Procure o menor elemento do _array_.
- Troque a posição do menor elemento com o primeiro.
- Volte ao primeiro passo e considere o _array_ a partir da próxima posição.
**Análise**
- Movimentações realizadas -> tempo de execução mais importante.