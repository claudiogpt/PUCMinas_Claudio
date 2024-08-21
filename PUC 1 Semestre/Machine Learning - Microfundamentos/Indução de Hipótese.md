#### Indução de H vs Viés Indutivo
1. **Exemplo**: Par \([x, f(x)]\) com entrada \(x\) e saída \(f(x)\).
2. **Indução**: Método para encontrar \(h\), uma aproximação de \(f\), usando exemplos.
3. **Hipótese**: \(h\) é a função aproximada. Consistente se \(h \approx f\) em todos os exemplos de treino.
4. **Generalização**: Habilidade de \(h\) prever dados não vistos. 
    - **Overfitting**: Alta previsão em treino, baixa em dados novos.
    - **Underfitting**: Baixa previsão até em treino.
5. **Viés Indutivo**: Preferência do algoritmo que limita o espaço de busca de \(h\).
	1. Cada algoritmo ou máquina vai ter diferentes viéses indutivos, importante conhecê-los.
#### Clusterização
- Muito útil para expandir o "label" de uma base de dados, não supervisionado.
### Aprendizado Semi-supervisionado
- Mistura dados com label e dados sem label.
#### Aprendizado Por Reforço
- Aprende minimizando risco ou maximizando retorno.
### Regressão
- **Redundância**
	- Não é importante em modelos mais robustos, em regressões mais simples pode ser um problema (utilizando algo redundante para corrigir um erro).
### Naive-Bayes
- Utiliza probabilidade condicional
	- Baseado no Teorema de Bayes
	**Subtipos**
		**Gaussian**
			Assume distribuição normal
		**Multinomial**
			Útil  para dados discretos
		**Bernoulli**
			Binário, útil para características de presença/ausência
		**Complement**
			Variação do Multinomial, melhor para dados desbalanceados
	**Vantagens**
		Simples
		Rápido
		Funciona bem com alta dimensionalidade
	**Desvantagens**
		Assunção de independência pode ser irrealista
		Sensível a características irrelevantes.
- Este modelo é eficaz para tarefas de classificação onde as características são condicionalmente independentes.
###### Correção de Laplace
- Técnica de alisamento usada em modelos probabilísticos, como o Naive Bayes, para lidar com categorias não vistas no treinamento.
**Vantagens:**
- Evita probabilidades zero em categorias não vistas.
- Melhora a generalização do modelo.
**Desvantagens:**
- Pode introduzir algum ruído se k for grande e o conjunto de dados for pequeno.
###### Variações
- **Naive Bayes** -> Assume independência entre as características.
- **Bayesian Networks** -> Captura dependências entre as características
	- (Talvez isso seja o que quero na hora de extrair informações sociais relevantes de uma base de dados).
###  Árvore de Decisão - TOP 3
- Alta interpretabilidade
###### Funcionamento
- Cada nó é um atributo
- Nós folha são do tipo Label
- Cada galho é etiquetado com um valor do atributo contido no nó pai
- Atributos não se repetem nos descendentes
	- Em exemplos de regressão pode ocorrer com sub-partições do domínio

### Contexto Atual em Machine Learning

##### Métodos de Seleção de Atributos
1. **Ganho de Informação (ID3)**: Utiliza a entropia para selecionar o atributo que proporciona maior ganho de informação.
2. **Taxa de Ganho (C4.5, J48)**: Melhoria do ID3, normaliza o ganho de informação pelo "split information", útil para evitar bias em relação a atributos com muitos valores.
3. **Índice GINI (CART)**: Mede a impureza de um conjunto de dados, preferido quando se deseja partição binária.
4. **Redução de Variância (CART)**: Usado em árvores de regressão para minimizar a variância dos valores-alvo no nó.
##### Evitando Overfitting
1. **Parada Precoce**: Interrompe o crescimento da árvore quando não é estatisticamente relevante.
2. **Poda**: Gera a árvore completa e a poda posteriormente.
3. **Poda com Erro Reduzido**: Avalia o impacto na validação ao remover cada nó e seus descendentes.
4. **Divisão de Dados**: Uso de conjuntos de treinamento e validação.
5. **Repetição**: Continua o processo até que a poda seja prejudicial.
### Tendências
-  A tendência atual favorece algoritmos que podem automaticamente ajustar sua complexidade para evitar overfitting, enquanto ainda mantêm uma alta capacidade de generalização.
##### Importância da Normalização
- Vários algoritmos estatístico de regressão utilizam média e variância, por isso a normalização pode ser tão importante para os modelos
	- Viés indutivo de distribuição normal dos dados
## Redes Neurais
- Menos sensíveis a ruídos
	- Não tem que normalizar, fazendo açougue de dados e potencialmente gerando distorção de informação
- Consegue alcançar alta acurácia por ser possível de aumentar sempre a complexidade do modelo
**Parâmetros**
	Momentum -> tem comportamento mais assintótico previsível
	Erro Global -> média dos erros para todo o conjunto de base de testes
	Taxa de Aprendizado -> "tamanho do passo" até o mínimo global

### Métricas de Função Objetivo: Vantagens e Desvantagens
#### Mean Squared Error (MSE)
##### Vantagens:
- Simples e fácil de entender.
- Diferenciável, o que facilita o cálculo do gradiente.
- Sensível a outliers, o que pode ser útil se os outliers são importantes.
##### Desvantagens:
- Sensível a outliers, o que pode ser um problema se os outliers são ruídos.
- Pode não ser apropriado para problemas de classificação.
##### Quando usar:
- Em problemas de regressão.
- Quando você quer penalizar erros grandes.
#### Entropia Cruzada (Cross-Entropy)
##### Vantagens:
- Focada em probabilidades, o que a torna útil para problemas de classificação.
- Menos sensível a outliers em comparação com MSE.
##### Desvantagens:
- Mais difícil de interpretar que o MSE.
- Não é simétrica: penaliza mais a classificação incorreta de uma classe minoritária.
##### Quando usar:
- Em problemas de classificação.
- Quando você está trabalhando com probabilidades.
### Resumo:
- **MSE** é geralmente utilizado em problemas de regressão e é útil quando você quer que grandes erros sejam notados e penalizados.
- **Entropia Cruzada** é mais comum em problemas de classificação, especialmente aqueles onde a saída pode ser interpretada como a probabilidade de pertencer a certas classes.
## Cientista de Dados
- Tirar um tempo de "consultoria", auto treinamento de casos parecidos para buscar intuição necessária, dado o "espaço de meta-soluções" atual para resolução do problema em mãos.
------------------------
