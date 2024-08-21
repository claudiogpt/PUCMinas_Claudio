## Rede Neural Perceptron 
- Possui uma ou mais camadas com vários Neurônios artificiais.
##### Treinamento da Rede
- Após definir um conjunto de dados e parâmetros para o treinamento, então o treinamento começa.
##### Uso efetivo da rede
- Foi treinada agora ela é utilizada para prever respostas (ao ambiente,  modelos estatísticos).
### Treinamento 
**Taxa de aprendizado:** velocidade do aprendizado.
	**Se muito alta:** convergência pode demorar, ou nunca ocorrer(divergência).
	**Se muito baixa:** demora muito para convergir.
**Erro global:** média de todos os erros para o conjunto de dados teste.
**Época(Epoch):** passada pelos dados.
### Estratégia Simples de Treinamento
- Dado um conjunto de dados (entradas e saída), seguir os seguintes passos:
	1 -> Iniciar os valores dos pesos aleatoriamente,
	2 -> Para cada conjunto de dados calcular o erro na saída do neurônio;
		erro = saida desejada - saida ocorrida;
	3 -> Baseado no erro calcular o valor de cada peso
		Wx = Wx(Erro x TaxaAprendizado x Entrada);
	4 -> Repetir a partir do passo (2) até que o erroGlobal esteja abaixo de um limiar ou tenha-se completado um limite de Épocas.
##### Limitações 
- **Perceptron de uma camada:** tem dificuldade de representar funções não lineares ou modelos que separem linearmente os dados.
	Só é possível representar fuções lineares com uma única camada (ou com várias sem funções de ativação).
## Perceptron Multicamadas
**Motivações:**
- Superar as redes neurais perceptron de camada única
- Realiza aproximações de funções contínuas
- Todo o conjunto de dados pode ser separado por uma rede de 3 camadas
- Quase todo o conjunto de dados pode ser separado com uma rede de 2 camadas
**Camadas**
- 1 - Camada de dados
- 2 - Camada oculta
- 3 - Camada de saída
#### Estruturas
**Redes Feed-Foward**
- Single-layer ou multi-layer
- Implementam funções - não possuem estado interno
**Redes Concorrentes**
- Possuem ciclos direcionados com atraso - possuem estado interno
	**Ciclos direcionados com atraso:** refere-se à existência de conexões entre unidades ou neurônios que formam uma estrutura de grafo com direção e podem apresentar um atraso nas interações.
	**Estado interno:** indica que essas unidades ou neurônios têm a capacidade de manter informações internamente, ou seja, eles podem reter um estado que evolui ao longo do tempo à medida que a rede processa informações.
- **Redes de HopField:** implementam memória associativa.
	**Redes de Hopfield:** um tipo específico de rede neural que foi projetado para implementar memória associativa.
	**Memória associativa:** permite recuperar informações com base em associações ou padrões de entrada previamente aprendidos. Em outras palavras, essas redes podem lembrar e recuperar padrões de entrada com base em informações armazenadas.
- **Máquinas de Boltzman:** usa funções estocásticas de ativação
	**Máquinas de Boltzmann:** são um tipo de rede neural estocástica que utiliza funções de ativação estocásticas em suas unidades. 
	**Funções estocásticas de ativação:** introduzem elementos aleatórios nas decisões das unidades da rede, tornando o processo de aprendizado mais robusto e útil para otimização e amostragem em problemas complexos.
#### Back-Propagation
- Inicia-se os pesos com um valor aleatório
- Usando o *training set*, alimenta a rede com os valores de entrada e observa a saída
- Calcula o erro
- Ajusta os pesos para diminuir o erro (**back propagation** na rede), e repete o processo um número fixo de vezes ou até que o erro seja pequeno o suficiente.
##### Cuidados (Treinamento)
- Deve-se tomar cuidado para que o *training set* seja representativo do conjunto de entradas e saídas possíveis.
- Em casos de mudanças significativas na entrada/saída deve-se re-treinar o modelo.
- Pode-se fazer a rede adaptativa, de forma que ela continue sendo treinada durante a execução (aprendizado por reforço).
	Treinamento dinâmico
**Tipos de Treinamento**
- Por padrão (on-line, incremental) - ajusta pesos a cada padrão de treinamento apresentado,
- Por ciclo (batch) - ajusta pesos para depois apresentar todos os padrões de treinamento (considera um erro médio para um conjunto de padrões)
- Estático - tipologia fixa(ajusta somente os pesos)
- Dinâmico - tipologia ajustável(ajusta pesos e topologia)
	**Exemplos** Liquid neural networks, algoritmos genéticos.
**Algumas Dificuldades**
- Não existe uma regra eficiente para treinamento e para encontrar a arquitetura ideal. Processo experimental e possivelmente demorado.
- Algumas ferramentas oferecem recursos para ajudar a encontrar os parâmetros ideais (mas consome tempo).
	**HiperParâmetros -** servem para lidar com esse tipo de dificuldade, mas eles demandam tempo e sistemas computacionais bem optimizados.
- Variação de parâmetros é muito alta (qual a heurística ideal?).
	Não dá para mapear todo o espaço de heurísticas em um curto período.
- Mínimos locais
- Overfitting 
- Centenas de algoritmos de treinamento
	É preciso categorizar e segmentar o problema (cinto do batman).
## Aplicações - Perceptron Multicamadas
##### Predição de Vendas - Estratégia da Janela Deslizante
- Valores médios anuais de vendas
- Índice do volume de vendas do varejo brasileiro
- Supermercados/hipermercados
**Montagem da Base de Treinamento**
Ano1, Ano2, Ano3, Ano4, Ano5 -> Ano6
Ano2, Ano3, Ano4, Ano5, Ano6 -> Ano7
... e daí por diante
#### Sistema de Irrigação de uma Planta
- Controlar ventilação e irrigação com base na temperatura e humidade