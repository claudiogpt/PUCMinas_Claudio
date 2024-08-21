## Indução de Regras
- Supervisionado
- Classificação
- Usado como benchmark
### Indução
#### Forma
- A regra assuma a forma:
	- if L(antecedente) then R(consequente)
	- L -> R == R <- L == R :- L
- Normalmente as partes esquerda L e direita R são complexos sem atributos comuns entre eles.
- L = antecedente, cauda, corpo, condição ou premissa da regra.
- R = conclusão ou cabeça.
#### Arvores
- Tal como nas árvores de decisão, o conjunto de regras é disjunto (FND - Forma Normal Disjuntiva)
- A indução de árvores de decisão recursivamente divide os exemplos em subconjuntos menores, separando as classes das demais.
#### Algoritmo de Cobertura
- Chuta classes usando um exemplo.
- Adiciona novos atributos para restringir o espaço.
#### Algoritmo ZeroR
- Não cria regras.
- Atribui todo mundo à classe majoritária.
- Serve como baseline para avaliar a qualidade de modelos.