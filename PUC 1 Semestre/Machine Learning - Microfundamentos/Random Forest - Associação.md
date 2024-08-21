# Ensemble
- Refere-se à combinação de vários modelos individuais para produzir um modelo final que seja mais preciso e robusto do que qualquer um dos modelos individuais.
	- Votação (binário 0/1) - classificação
	- Ponderação (valores contínuos) - regressão
## Random Forest
#### Requisitos
- Classificadores devem ser independentes.
- Classificadores devem possuir desempenho superior à adivinhação (random guessing).
- Classificadores fracos possuem menor capacidade de classificação, mas podem se concentrar em características menos usuais da base de dados
	- Juntar modelos que se super-ajustam, de alta complexidade, pode ser inútil, as respostas tendem a ser a mesma
	- Modelos fracos (baixo poder de precisão) se concentram em características diferentes, a ponderação pode criar um espaço de solução mais completo
		- Analogia - pessoas com diferentes especialidades votando para uma solução complexas (mais complexa que a simples soma das especialidades).
	- Como assim? 
#### Utilidade
- Maximizar a performance do modelo (análises prescritivas).
	- Podem-ser utilizar métricas diversas
- Classificadores fracos criam espaços ortogonais, o ensemble cria uma solução mais complexa.
## Técnicas
- Bagging e Feature Selection
- Bootstraping
	- Seleção de Features -> Testa a melhor feature da árvore para diferentes recorte dos dados (se eu tenho 100 modelos e faço log_2, eu testo 10 aleatórios para cada árvore).
		- Amostragem sem reposição (cada elemento só é sorteado uma vez).
	- Posso podar a árvore prematuramente (height max == 5) para gerar árvores mais fracas e fazer o agregado delas.
- Bagging
	- Tentativa de mostrar os atributos complicados da minha base de dados
	- Amostragem com reposição.
		- Pode ser sorteado mais de uma vez(algum elemento).
		- Variação ligeira entre as árvores, elementos e sorteamentos se repetem, mas distribuição estatística varia.
	**Num_Estimadores:** principal hiperâmetro.
		Difícil otimizar por ser aleatória.
		Guardar o seed para fazer testes em ambiente controlado. 
### Bagging
- Processo em paralelo
### Boosting
- Melhora  "qualquer" algoritmo para precisão que permita pesos nas Arestas.
- Sequencial, muda o peso dos erros (é um protótipo de rede neural)
- Faz o teste de vários modelos de uma vez melhorando a performance pra você
### ADABOOST
- Top 10 machine learning
- Pode usar qualquer classificador fraco que permita colocar pesos na base de registros da base de dados
- É rápido, pois faz apenas uma passada na base a cada iteração
- Mudança de mentalidade
	- Quero achar um classificador fraco, marginalmente melhor que a adivinhação
	- Adaboost atribui pesos diferenciados a cada modelo de classificação.
- Frequentemente chega a 100% de acerto.
	- Se não dá certo pode indicar erro em outras partes do processo.
##### Resumo do Funcionamento
Normalmente os algoritmos de boosting se concentram nos exemplos mais difíceis (aqueles que foram incorretamente classificados nas etapas anteriores), utilizando pesos nos registros.
- Aumenta o peso dos exemplos classificados erroneamente.
- Diminui o peso dos exemplos classificados corretamente.
A combinação dos modelos é feita no final pela maioria ponderada dos votos.

----
# Regras de Associação
- Frequentemente usado para regras de cestos de compras
- Não supervisionado
- Bom para encontrar estruturas em bases de dados
### Utilidade
- Encontrar correlações entre conjuntos de itens (frequentes)
- Encontrar relações causais
- Alta explicabilidade
### Requisitos
- Itens possuem valores binários
	- V, F
	- Pertence, Não Pertence
- ItemSet
	- SubConjunto de Items onde os valores são verdadeiros (apareceram juntos)
	- São ordenados
		- Para facilitar a procura dos algoritmos
	- Tabela de tamanho 10 tem F(10 - i) recursivo, caso base 0 ItemSets.

### Métricas
Se X então Y (X e Y são conjuntos de items)
#### Suporte 
- sup(A, B) = transações com A e B/total de transações
#### Confiança
- conf (A -> B) = transações que suportam (A + B)/transações que suportam A
	- Testa se A então B (A -> B)
- conf (B -> A) = transações que suportam (B + A)/transações que suportam B
	- Testa se B então A (B -> A) 
### Frequent ItemSets
- Subdivisões associadas da tabela principal, com a taxa de suporte do lado (o quanto aparece, o quão frequente é).
### Algoritmo Apriori 
 - Fase 1
	 - Descobrir todos os subconjuntos de itens com suporte maior ou igual ao mínimo suporte especificado
	 - Subset de um item frequente também é frequente
- Fase 2
	- Descobrir regras de associação a partir dos itens frequentes com fator de confiança acima de um threshold especificado
### FP-Growth
- Percebeu-se que a quantidade de Scans na base de dados era ineficiente
- Não gera candidatos
- Mais eficiente e escalável que o método Apriori
**Estrutura**
- Percorre o banco de dados apenas duas vezes
	- Phase 1
		Constrói uma FP-Tree (Quasi-Linear, n log n)
	- Phase 2
		Extrái item-sets frequentes diretamente da FP-Tree
### Medidas de Interesse
- Lift (Mais relevante)
	- Checar concorrência aleatória dos concorrentes ou consequentes
- Confiança
- Laplace