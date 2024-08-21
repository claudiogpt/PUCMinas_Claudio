### Tipos de Aprendizado
## Aprendizado supervisionado
- Dado de treinamento possui rótulos conhecidos.
- Cria modelo para fazer previsões e se autocorrige quando as previsões são ruins até atingir acurácia aceitável (utilizando a função de erro).
	Prever um atributo selecionado, domínio do problema e da solução bem circunscritos.
## Aprendizado não supervisionado
- Dado não é rotulado ou não possui resultado conhecido.
- Modelo deduz estruturas a partir da entrega.
	**Tipos de Estrutura**
		Topologias
		Agrupamento de Dados por semelhança
		Segmentação de Dados por diferença
## Aprendizado semi-supervisionado
- Mistura dados rotulados e não rotulados.
	Muito caro rotular uma base de dados (rotula-se apenas uma parte)
- Existe uma previsão desejável, mas modelo precisa organizar estruturas.
	Se utiliza mini-batches rotulados,
	Se advinha o resto que não é rotulado,
	Em bases de dados muito grandes o erro ocorre em Edge Cases (Erros de Fronteira),
	Resultados melhores que em apenas pequenas bases de dados rotuladas, por ser capaz de extrair mais informação.
## Aprendizado por reforço
- Um agente explorar um ambiente. A cada instante de tempo o agente está em um _estado_ qualquer, executa uma _ação_, vai para um novo _estado_ e recebe uma _recompensa_.
- Problema da aprendizagem por reforço consiste em escolher uma _política de ações (heurística)_ que maximize o total de recompensas recebidas pelo agente.
	Aposta-se em comportamentos emergentes,
	Frequentemente se descobrem novas estratégias não pensadas pelo ser humano,
	Bom para estratégias de exploração,
	Construção de mapas (vários sentidos - como espaços de solução).
## Aprendizado profundo (_deep learning_)
- O aprendizado profundo também possui aprendizado supervisionado, não supervisionado e de reforço.
	Baseado em redes neurais.
- O objetivo é utilizar modelos de redes neurais extremamente complexos e com muitas camadas para identificar estruturas em problemas onde os dados não são claramente estruturados. Adequado para extrair recursos significativos de dados brutos.
	Possui várias camadas intermediárias na tomada de decisão, não necessariamente compreensíveis ao ser humano,
		camadas de neurônios
	**Hipótese:** se essas etapas puderem ser destrinchadas, podemos descobrir novas heurísticas para soluções de problemas, sobre cognição no geral e no funcionamento das máquinas.
## Tarefas de Aprendizado de Máquina
#### Descritivas
- **Agrupamento**
	**Análise de Agrupamento(Clustering)**
		Segmenta automaticamente a base de dados em grupos por suas similaridades e diferenças,
- **Associação**
	Encontrar padrões frequentes, associações, correlações entre conjunto de itens ou objetos em um repositório de informação,
		**Ex.** Quem compra A compra B em 60% das vezes
#### Preditivas
- **Classificação**
	-> Classificação é uma das tarefas utilizadas para extrair modelos que descrevem classes de dados e também para predizer tendências dos dados,
	-> É usada para construir ou prever atributos categóricos a partir de um conjunto de outros dados.
		 **Etapas**: geração do modelo -> validação -> uso do modelo
	**OBS:** rede neural ou árvore de decisão, qual o mais adequado para uma dada tarefa de classificação?
- **Regressão**
	-> Conjunto de técnicas estatísticas ou computacionais para estimar a relação entre variáveis ou atributos,
	-> Geralmente utilizada para previsão de valores futuros baseados em dados passados.
##### **Tarefa por Algoritmo**
- **Agrupamento**
	K-Means
- **Associação**
	Apriori
- **Classificação**
	Árvore de decisão
- **Regressão**
	Redes Neurais


