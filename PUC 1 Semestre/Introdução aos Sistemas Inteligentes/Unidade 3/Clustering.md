## Clustering 
- **Exemplos de Utilização**
	Perfis de clientes, assuntos mais falados (problemas não tão bem definidos).
- Pode ser subdividido em dois subgrupos:
	-> **_hard clustering_**: cada registro pertence a um cluster.
	-> **_soft clustering_**: cada registro possui uma probabilidade de pertencer a um ou mais _clusters_.
	Os algoritmos de agrupamento variam na forma como eles distribuem os _clusters_ no espaço de dados (tipo diagrama de Venn). Os métodos de agrupamento podem ser:
	- **Modelos baseado em centroides (ou modelos de particionamento):** A similaridade dos elementos é definida em termos de sua proximidade de um ponto de dados com o centroide dos clusters. O algoritmo de agrupamento K-Means é um algoritmo mais popular dessa categoria.
	- **Modelos de densidade:** Esses modelos examinam a densidade de diferentes regiões do espaço de dados e atribui os pontos em regiões de mesma densidade pertencem ao mesmo cluster. O DBSCAN é um algoritmo clássico de agrupamento por densidade.
	- **Modelos hierárquicos (de conectividade):** Podem ser aglomerativos ou divisórios. Na abordagem aglomerativa, todos os pontos de dados começam em clusters separados e, em seguida, vão sendo agregados pela menor distância. Nos métodos divisórios, todos os pontos de dados são classificados como um único cluster e particionados pela maior distância. AGNES é um algoritmo famoso que utiliza a abordagem aglomerativa.
- Cria novos rótulos para os grupos.
- É não supervisionado.
- Muito bom para reduzir o trabalho para grupos significantes, em vez de testar todas as possibilidades (dividir e conquistar);
- Bom como etapa de tratamento de dados para servir como entrada em outros modelos de treinamento.
	Funções de transformação subsequentes, minimizando a necessidade de ação humana.
##### Aplicações
- Distribuição e pré-processamento de dados,
- Proc. de imagens (segmentação); economia; marketing,
- WWW (Classificação de documentos, padrões de acesso),
- Agricultura (áreas de uso de terra); planejamento de cidades (agrupar casas de acordo com tipos, valores, localização).
##### Medidas de Similaridade
**Processo:**
	1 - Normalizar os Dados
	2 - Calcular distância
**Normalização:**
	Dados entre 0 e 1
	**Cada Coluna**
		Maior dado = 1,
		Menor dado = 0,
		Outros -> Proporcionais (à normalização)
**Distância**
	Nesse caso é a Distância Euclidiana
		$d(p, q) = \sqrt{\sum_{i=1}^{n}(q_i - p_i)^2}$
##### Medidas de Outros Tipos de Atributos
**Variáveis Binárias**
	Simétricas (M/F)
	Assimétricas (Positivo/Negativo - Exame Médico)
		Casos onde apenas o positivo importa (por exemplo)
**Variáveis Nominais**
	Generalização de var. binárias multi-atributo.
		**Ex.** vermelho, amarelo, azul, verde.
**Variáveis Ordinárias**
	Uma variável ordinária em que a ordem dos valores é importante.
		**Ex.** Medalha. **Valores:** bronze, prata, ouro.
### K-Means
- K-means (k-médias) é um algoritmo de agrupamento iterativo que visa encontrar máximos locais em cada iteração.
	Os 6 passos do K-means são etapas:
	1. Definir o número de clusters K.
	2. Selecionar aleatoriamente K pontos no espaço de dados.
	3. Alocar os dados ao cluster pertencente ao centróide mais próximo.
	4. Computar os centróides de cada cluster a partir dos pontos alocados.
	5. Reatribuir cada ponto ao centróide mais próximo.
	6. Repetir os passos 4 e 5 até que não haja mais realocação de dados.
- Precisa de distância e calcular a média entre objetos de um cluster.
- Foge de local minima, não há garantia de ser global, é eficiente pela velocidade.
- Limitar o número de interações para não entrar em loop infinito.
### Regras de Associação
**Objetivo**
	 Associações, correlações entre conjuntos de items ou objetos de um banco de dados transacional/relacional ou outro repositório de informações.
**Aplicações**
- Análise de cestas de compra/marketing/portfólio.
- Quais subsequentes compras após ter comprado um PC?
- DNA sensitivo a uma nova droga.
- Turistas que querem ir pro EUA também aceitam ir para a Europa.
- **Obs:** todas as aplicações são aproximações em um espaço de conhecimentos, a resposta é dada por proximidade.
### Árvores de Decisão
- Tipo de algoritmo para aprendizado supervisionado. 
- Persistem entre as técnicas mais utilizadas atualmente. 
- Pode ser utilizada tanto para classificação quanto para regressão. 
- Na análise de decisão, uma árvore de decisão pode ser usada para representar visual e explicitamente decisões e tomada de decisão. como o nome diz, ele usa um modelo de decisões em forma de árvore.
