### Cientista de Dados
**Conjunga:**
- Ciência da Computação,
- Conhecimento Estatístico,
- Expertise do Domínio do Conhecimento.
### Processo da Ciência de Dados
- Fazer uma pergunta interessante/relevante,
- Coletar dados,
- Explorar dados,
- Modelar dados,
- Comunicar e visualizar os resultados (algumas partes do processo são intercambiáveis entre si).
### Processo Referência
- Data Science LifeCicle;
### Feature Engineering
- Eliminar dados que atrapalham no modelo,
- Transformação de dados (geralmente matemática),
## Fases
- Business Understanding -> data acquisition && understanding/ modeling -> deployment/scoring.
### Definição do Problema
Frequentemente subestimada.
**Define:**
- Dados a serem coletados,
- Modelo a ser treinado,
**Caso 1:**
	Rei quer casar uma população.
	**Definição do Problema(Pergunta):** Identificar todos os casamentos possíveis da população de 50.000 habitantes utilizando compatibilidade por horóscopo.
		Enriquecer a base de dados regras dos signos. 
**Caso 2:**
	Vendas de uma empresa estão caindo, como posso alavancar a empresa para uma alta taxa de vendas? 
		**Possíveis métodos:**
			Alinhamento de variáveis (identificar causas) -> vendas caíram por que estoques estão baixos?
				Remanejar a pergunta -> baixa em estoque está correlacionada com a queda nas vendas?
### Redefinição Precisa do Problema
- Problema abstrato -> um ou mais problemas específicos.
- É necessário utilizar dados, fatos e julgamentos.
	**Fatos:** Circunstâncias que causam diretamente o problema.
	**Julgamentos:** Observações a serem disputadas ou decididas.
**Caso 3:**
	**Análise de risco para acidentes de carro:**
		**Fatos (Causas):**
			Imperícia,
			Imprudência,
			Negligência,
		**Julgamentos (Hipóteses):**
			Qual o perfil do motorista de cada veículo?
			Quais os perfis dos veículos?
			Violaram alguma lei de trânsito?
**Caso 4:**
	**Devolução de Produtos:**
		**Fatos:**
			Defeito na envoltura,
			Fora da validade,
			Produto estragado,
			Fora da especificação.
		**Julgamentos (Hipóteses)**
			Quem fabrica a envoltura?
			Quem comercializa o produto?
			Como o produto foi estocado?
			Como o produto é embalado?
			Como o produto é transportado?
### Tipos de Dados
A solução de um problema depende dos tipos de dados que nós temos disponíveis.
##### Quantitativos
- Discretos
	Faixa de valores distintas (não pertence aos números reais)
		**Ex:** inteiros, ímpares, pares, primos...     
- Contínuos
	Pertence aos números reais (apesar de poderem ser reduzidos a subconjuntos dos números reais(como um range)).
- Normalizados (0...1)
	**Ex:**
		Capacidade ociosa: 70% ociosa(0.7).
		Andamento da Operação: 90% concluída.
- Não normalizados (min...max)
	Idade, temperatura (numérico).
**Qualitativos**
- Nominais/Categóricos
	Não conseguimos ordenar. 
	**Binários:**
		Dois valores,
			**Ex:** Sim/Não, Comprou/Não Comprou.
		**Simétricos:**
			Possuem a mesma importância.
		**Assimétricos:**
			Apenas os positivos são relevantes.
				**Ex:** compras de supermercado (média de 40 itens). Assistir um filme (tem muito mais filmes que alguém consegue assistir).
	**Multivalorados:**
		Polinomiais/Categóricos não ordinais
		**Exemplo:**
			**Regiões de BH:** centro, sul, centro-sul, leste, oeste...
- Ordinais
	Conseguimos ordenar.
		**Ex:** Pequeno -> Médio -> Grande.
	**Categóricos Ordinais**
		**Exemplos:**
			**Faixa etária:** criança, adulto, idoso...
### Dados Assimétricos
- Em geral dados esparsos (muitos zeros?) são assimétricos.
	**Exemplos:** termos de um documento, sintomas de doenças.
		**Termo em um documento:** frequentemente um documento tem muitos termos não usados, por isso assimétrico.
		**Sintomas:** as vezes a ausência de um sintoma ocorre (nos dados) por que ele não foi testado, não por que ele não existiu. Ou as vezes vários sintomas não ocorrem para a mesma infecção/doenças.
### Dados Quantitativos
##### Escala Intervalar
- Define faixas de valores e relação entre eles. Nem sempre permitem definir a razão entre os valores.
	**Exemplo:**  
		Graus Celsius não permite razão (zero arbitrário).
		Temperatura de Kelvin permite razão (zero absoluto).
**Escala Racional**
	Números possuem significado absoluto (zero absoluto).
		**Exemplo:**
			Número de doentes em um hospital, peso(KG).
**Escala de Dados Quantitativos Podem Ser (Especialmente os Racionais):**
	Normalizados,
	Não Normalizados.
## Estatística Descritiva
- Ramo da estatística que aplica técnicas para descrever e sumarizar um conjunto de dados. Seu objetivo é organizar, sumarizar dados o que a torna uma disciplina independente.
- Números que resumem as propriedades de dados.
#### Medidas e Propriedades
**Frequência de um Dado**
- Número de vezes que um dado ocorre em um conjunto,
- Frequência absoluta (número) e relativa(percentagem) de um dado.
**Média**
- Medida mais comum  -> somatório de n termos, dividido por n.
- Muito sensível a outliers. Em um conjunto pequeno de dados, por exemplo, um outlier pode alterar em muito a média.
**Mediana**
- Valor que separa as duas metades de um termo (metade maior/metade menor).
	Se for impar: $$x_{n/2 + 1}$$
	Se for par: $$\frac{1}{2}x_{n/2}+x_{n/2+1}$$
**Moda**
- Valor mais frequente/comum (que mais se repete) da amostra.
**Percentil**
- Divide a amostra em 100 partes iguais (em ordem crescente).
- Cada uma com uma percentagem de dados igual (1/100).
- O k-ésimo percentil Pk é o valor X(Xk) que corresponde à frequência cumulativa de n.
- Percentil é diferente de percentual.
	- **Percentual**: Refere-se a uma proporção ou uma fração de uma quantidade total, geralmente expressa em termos de porcentagem. Por exemplo, se você diz que um estudante obteve um percentual de acertos de 80% em um teste, isso significa que ele acertou 80% das questões em relação ao total de questões.
	- **Percentil**: Refere-se a uma medida estatística que indica a posição relativa de um valor em uma distribuição de dados. O percentil divide um conjunto de dados em 100 partes iguais, onde cada parte contém uma porcentagem dos valores. Por exemplo, o percentil 75 (também conhecido como Q3) indica que 75% dos valores estão abaixo desse ponto quando os dados estão ordenados.
### Medidas de Espalhamento
**Intervalo**
- Diferença entre o máximo e o mínimo,
	**intervalo(x) = max(x) - min(x)**
**Variância**
- Dado um conjunto de dados, a variância é uma medida de dispersão que mostra o quão distante cada valor do conjunto está do central (média).
- Quanto menor é a variância, mais próximos os valores estão da média; quanto maior, mais os valores estão distantes da média.
$$Var\;(amostral)\; = \frac{(x_1-X)^2+(x_2-X)^2+(x_3-X)^2+...+(x_n-X)^2}{n-1}$$
**Desvio Padrão**
- O desvio padrão é capaz de identificar o "erro" em um conjunto de dados, caso quiséssemos substituir um dos valores coletados pela média aritmética.
- O desvio padrão aparece junto à média aritmética informando o quão confiável é um valor.
$$média\;aritmética\;(x)\pm desvio\;padrão\;(dp)$$
- É a raiz quadrada da variância:
$$\sigma = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2}$$
- Ambos também são sensíveis a outliers.

### ETL - Extract Transform Load
##### Business Intelligence 
- Apoio à tomada de decisão humana, apoiada por dados(o mais próximo que temos de fatos).
- Conjunto de técnicas para a estruturação, enriquecimento de dados para ajudar uma empresa na tomada de decisão.

**Elementos/Tecnologias**
- Relatórios
- Ferramentas de processamento analítico
- Gerenciamento de indicadores de desempenho
- Análise descritiva e preditiva
	Estatística descritiva e predição através do aprendizado com padrões
- Técnicas de IA
- Visualização de Dados
	Relatórios sofisticados

**Processo ETL (Extract Tranform Load)**
- Facilita importação, exportação, transformação de dados heterogêneos
- Integração, consolidação e agrupamento de informações
- Pode-se utilizar informações comerciais ou nossos próprios algoritmos/scripts
- Areas intermediarias podem ser necessárias (stagging area)
	**Ex:** pasta temporária de arquivamento de fotos antes de transferir para outra
- Comum requisitar 80% do tempo

**Etapas**
	**Entradas**
		- Bancos de Dados
		- Redes sociais
		- Arquivos txt
		- Dispositivos
		- CSV, EXCEL
	**Processo**
		- Extrair
			Dados Operacionais, Dados Externos
		- Transformar
			Limpar
			Reconciliar
			Aprimorar
			Sumarizar
			Agregar
		- Carregar
			Organizar
			Combinar fontes
			Popular Sob Demanda
	**Saídas**
		- Repositório Estruturado

#### Limpeza de Dados
- DW (Data Warehouse) -> tomada de decisão / dados precisam estar corretos
- Grande quantidade de dados -> erros e anomalias nos dados
	**Como:**
		tamanho inconsistente de campos, descrições inconsistentes, atribuição inconsistente de valores, entradas erradas, violação de restrição de integridade
#### Transformação de Dados
- Conjunto de operações em cada um dos registros (linhas) antes de ser enviada ao destino
#### Carga dos Dados
- No final os dados devem ser enviados para o repositório de destino
- Um pré-processamento adicional pode ser requerido 
	sumarização
	agregação
	checagem de restrições de integridade
- Tipicamente feito em lotes
## Preparação de Dados
- Conjunto de tarefas de pré-processamento, realizadas manualmente ou com o uso de ferramentas, visando deixar os dados aptos a serem explorados
- Geralmente consome 70-80% do projeto
- **Qualidade:** devemos garantir que estejam padronizados e estatisticamente consistentes
	**Exemplos:** datas, unidades de medida
#### Tarefas de Pre-processamento
- Eliminação de atributos
- Integração dos dados (?)
- Amostragem dos dados
- Balanceamento dos dados
- Limpeza de dados
- Redução de dimensionalidade
- Transformação dos dados
**Resumo**
- Atributos: remoção e seleção de colunas
- Registros: remoção e seleção de linhas
- Transformação dos dados
#### Atributos 
- Alguns atributos podem não ser importantes e devem ser eliminados
	análise estatística da relevância dos dados / julgamento da relevância dos dados
- Remoção de dimensionalidade (_feature engineering_)
#### Registros
Podem conter:
- Dados conflitantes: registros duplos
- Dados incorretos: entradas errôneas, ruídos
- Dados omissos ou faltantes
- Outliers (geralmente são removidos, mas podem ser analisados especificamente)
	Variação muito grande do conjunto de dados.
- Limpeza pode ser necessária
**Ruídos**
- Modificações nos valores originais
- Ruídos de leitura 
- Ruídos e medição
- Ruídos de fundo
**Outliers**
- Dados com características diferentes da maioria dos dados do dataset
**Estratégias para dados omissos ou incompletos**
- Remoção dos registros 
- Novos dados inferidos ou estimados
- Dados podem ser tratados como casos especiais
- Seleção usando amostragem
- Uma amostra pode ser significante para uma análise
### Transformação de Dados
**Agregação de Colunas**
- Combina dois ou mais atributos em um
**Agregação de Linhas**
- Resumir registros em função de alguns atributos
- Funções de agregação: contagem, soma, média, moda, desvio padrão.
- Média dos valores de cidades podem representar um estado (próximo o suficiente)
**Tipo de Dados**
- Algoritmos e ferramentas podem ser limitados quanto ao tipo e formato dos dados
- Algumas conversões podem ser necessárias
	-> categórico não ordinal para binominal
	-> categórico ordinal para numérico
	-> numérico para numérico
		mudança de escala/normalização
##### Ferramentas de Pré-Processamento
- Planilhas eletrônicas
- Inteligências Artificiais
- Ferramentas de ETL
- Ferramentas de Machine Learning
	Orange Data Mining por exemplo.
- Programação: algoritmos/códigos próprios/scripts

## BIG DATA
- Acredita-se que 99,5% dos dados produzidos nunca são analisados (Harvard Business Review, 2020).
	Se pensar melhor existem os dados não capturados, produzidos também, 
	**Observação Pessoal** dados são fragmentos analíticos da realidade pelo homem.
**Big Data**
- “_Big data_ _is high-_**_volume_**_, high-_**_velocity_** _and high-_**_variety_** _information assets that demand_ **_cost-effective_**_,_ **_innovative_** _forms of information processing for_ **_enhanced insight and decision making_**.” – Gartner
**5V's da Big Data**
- **Volume de Dados**
	Está relacionado à escala dos dados. Coletá-los, armazená-los e acessá-los sob demanda é um grande desafio do Big Data.
- **Variedade**
	Está relacionado aos tipos de dados obtidos.  Hoje em dia, é necessário processarmos dados de textos do notícias, blogs, comentários de clientes, avaliações de produtos, etc. Tem-se milhares de dados multimídia, tais como vídeo, imagem e áudio (fala e música). Temos ainda a internet das coisas, que nos provê um oceano de dados de sensores vindo de dispositivos vestíveis, sistemas de monitoramento, geolocalização, sensores e ouros muitos mais. Conseguir extrair estruturas deste lago de dados é outro desafio do Big Data.
- **Velocidade**
	Processar variedade e volume não resolve os problemas das empresas. Velocidade dos dados nos apresenta como um grande desafio, o dado de hoje já pode ser velho amanhã.
- **Veracidade**
	A qualidade dos dados é um dos maiores desafios do Big Data atualmente. Ruídos na coleta, incapacidade de se determinar o instante em que o dado foi produzido, entre diversos outros problemas tornam a qualidade dos dados ruim. Volume não é suficiente.
- **Valor**
	A informação deve apoiar a tomada de decisão. Mas para os dados se tornarem informação, eles precisam ser analisados por diversas técnicas e ferramentas de Análise de dados (chamada de _Analytics_). Dado coletado e não armazenado  não vale nada, dados não transformado em conhecimento ou utilizado para decisão também não. A cultura de tratar o dado como algo valioso gerou uma ganância nas empresas pela coleta e armazenamento dos dados, como se o dado em si fosse como o ouro. Mas o dado sem a análise não produz valor, e escondê-lo do mundo impede o avanço da sociedade como um todo.
## Estratégia de Dados
- Entender estratégia de dados nos ajuda a entender perguntas que gostaríamos de responder e que tipo de dados eu preciso para respondê-las
	**Ex:**
		Captar novos clientes, aumentar engajamentos de clientes.
##### Tipos de Dados Coletados
**Dados Pessoais:**
	Esta categoria inclui informações de identificação pessoal e não pessoal. As principais informações pessoais que são coletadas são idade, sexo, grau de instrução, entre outras informações demográficas que podem ajudar a construir um perfil do usuário. 
	**Identificação não pessoal:** incluem endereço IP da máquina, fornecido pelo provedor, cookies do navegador da web e IDs de dispositivo, que seu laptop e dispositivo móvel possuem. Essas informações ajudam a construir a sua impressão digital.
**Dados de engajamento**
	Este tipo de dado detalha como os consumidores interagem com o site da empresa, aplicativos móveis, páginas de mídia social, e-mails, anúncios pagos e canais de atendimento ao cliente. Um exemplo famoso de indicador de engajamento é o NPS (_Net Promoter Score_), mas toda vez que um usuário curte um post de uma empresa, ele está fornecendo um dado precioso de engajamento.
**Dados Comportamentais**
	Esta categoria inclui detalhes transacionais, como históricos de compra, informações de uso do produto (por exemplo, ações repetidas) e dados qualitativos (por exemplo, informações de movimento do mouse).
**Dados de Atitude**
	Métricas de satisfação do consumidor, critérios de compra, conveniência do produto e muito mais. Mostram se o usuário está propenso a fazer uma compra ou a se inscrever em um serviço. Aqueles questionários com perguntas na escala de Likert, com informações como: concordo, discordo e indiferente, por exemplo, são normalmente coletas de dados de atitude.
### Como utilizar dados
**Para Melhorar a Experiência do Cliente**
	Ao analisar o comportamento do cliente, bem como um vasto acervo de comentários e feedback, as empresas podem modificar agilmente sua presença digital, bens ou serviços para melhor atender ao mercado atual. As empresas buscam cada vez mais a individualização para a tomada de decisão. 
		Personalização do serviço, serviço sobre medida (sob quais vieses? maximizar consumo, satisfação, felicidade?).
 **Para refinar a estratégia de marketing de uma empresa**
	**Dados contextualizados:** podem ajudar as empresas a entender como os consumidores estão se envolvendo e respondendo às suas campanhas de marketing. 
	Entender o que os consumidores desejam com base no que já fizeram (sistemas de recomendação).
**Para transformar os dados em fluxo de caixa**
	A venda de dados é um negócio altamente lucrativo. Esta indústria de compra e venda de dados surgiu com o Big Data, e gerou novas oportunidades de receita.
**Para proteger mais dados****
	Algumas empresas usam dados do consumidor para proteger informações mais confidenciais. **Exemplo:** instituições financeiras podem utilizar dados de reconhecimento de voz ou outro dado biométrico para autorizar um usuário a acessar suas informações financeiras e/ou protegê-los contra tentativas de fraude.
#### Questões Legais e Regulamentares
A **LGPD e GDPR** são leis que regulamentam a coleta, a utilização e o tratamento dos dados pessoais de cidadãos no **Brasil e na União Europeia.** 
Definem a necessidade do consentimento do usuário para que a coleta seja feita. Elas determinam critérios a serem adotados na coleta e armazenamento de dados sensíveis, principalmente no que se refere à proteção desses dados. Elas também definem responsabilidades, como quem é o controlador e quem é o operador do dado.

- [Lei Links to an external site.](http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm)[Geral de Proteção de DadosLinks to an external site.](http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm) (LGPD)
- [General Data Protection RegulationLinks to an external site.](https://gdpr-info.eu/) (GDPR)

Sempre que for coletar dados de usuários, é interessante que essa legislação seja consultada. A ajuda de uma empresa especializada em direito digital também pode ser recomendável. Alguns sistemas já possuem "conformidade" com essas regulamentações. O que significa que eles já possuem os níveis de segurança necessários para o armazenamento e proteção dos dados, além de já possuírem os recursos tecnológicos para automatizar a obtenção do consentimento dos mesmos.
## Data Analytics
##### Maturidade em Análise de Dados
**Percebendo e Respondendo**
	**Primeiro cenário:** a análise de dados é mais simples, mais barata e mais rápida. Perceber o que está acontecendo e responder ao cenário descoberto, de forma reativa. 
	**Tipos de análise:** **descritivas** e **diagnósticas**.
**Prevendo e Agindo**
	**Segundo cenário:** a análise dos dados se torna mais complexa. É muito difícil se atingir essa maturidade sem uma equipe especializada em análise de dados. Aqui nós podemos tomar decisões e agir de forma proativa, antecipando o que irá acontecer. 
	**Tipos de análise:** **preditivas** e **prescritivas**.
##### 4 Tipos de Análise
**Descritiva**
	A análise descritiva é a mais fundamental e está relacionada com a descrição do mundo, em geral, utilizando estatística. A pergunta que respondemos é "O que aconteceu?"
	**Alguns exemplos de perguntas reais seriam:** "Qual foi a receita deste mês? Quais foram os 5 produtos mais vendidos?
**Diagnóstica**
	A análise diagnóstica muitas vezes não é dissociada da análise descritiva. A única diferença está na utilização de comparações e correlações estatísticas para identificar _insights_ (intuições) para compreender o presente.
	**Algumas perguntas possíveis seriam**: "Quais os melhores dias para eu vender o meu produto X? Que tipos de produtos são normalmente comprados juntos?"
**Preditiva**
	A análise preditiva cria modelos que permitem prever potenciais resultados e nos permite se preparar para o futuro.
	**Algumas perguntas possíveis:** "Qual é a previsão de demanda para o produto X no próximo mês? Qual o número esperado de visitantes do museu na próxima semana?"
**Prescritiva**
	A análise prescritiva avança um pouco além da análise preditiva. Utilizaremos a tecnologia para nos sugerir um curso de ação, um caminho a ser seguido baseados nos dados analisados.
	**Algumas perguntas possíveis:** "Como eu posso vender mais produtos X? Como eu posso aumentar o engajamento dos meus alunos na sala de aula virtual?"
**BONUS, Cognitiva**
	Se relaciona com o uso de tecnologias autônomas que aprendem e se adaptam sem a intervenção humana. Isso envolve monitoramento, análise interação e ação em tempo-real. A aplicação mais famosa no momento que utiliza este tipo de análise são os carros autônomos, que precisam reagir em tempo real a milhares de dados coletados a cada segundo, entendendo o ambiente e decidindo sobre a melhor ação a ser tomada de forma automática, ou seja, sem que seja aprovado ou validado pelo homem.
	**Análise Cognitiva:** emulação de uma "inteligência completa", definindo ações, metas, percebendo o ambiente e descriminando entre possíveis caminhos.

**OBS**
	-> Limpeza de dados é uma das áreas mais custosas na ciência de dados, como podemos melhorá-la, automatizá-la?
	-> Utilidade temporal da ciência de dados, morremos mas os dados e análises e sistemas ficam para as próximas gerações.  Se morremos simplesmente com o conhecimento nossa expertise "vai embora do mundo", como consolidar esse tipo de conhecimento? Formalizando-os para análise póstuma.
## Visualização de Dados
- Maior volumes de dados -> a visualização e tratamento desses dados em geral se tornam mais importantes.
- Algumas tecnologias permitem e exploram a análise de dados complexos.
- Data Visualization -> uma das áreas mais importantes em Ciência de Dados.
**Para quê?**
	-> Maneira resumida de transmitir os dados,
	-> Forma de comunicar dados complexos,
	-> Visão é um dos nossos sentidos mais intensos.
		Mais de 90% da informação (cultural) que consumimos passa pela visão.
		50% dos nossos neurônios são dedicados ao processamento visual.
		Dados visuais atraem mais atenção.
		Figuras aumentam nosso interesse na leitura.
		Retenção do conteúdo na visão é melhor.
**Vantagens:**
	Decisões podem ser mais ágeis,
	Mais pessoas engajadas,
	Gráficos com mensagens claras passam mais atenção,
	Maior acesso, melhora a compreensão dos fatos.
		Contorna o "analfabetismo funcional" de textos mais complexos.
**Ferramentas:**
- Google Planilhas & Microsoft Excel
- Tableau, GapMinder, GoogleDataStudio, PowerBI.
- QlikView, R Studio, Visual.ly, Tangle, iCharts, SmartData.
- Python:
	Matlplotlib, Seaborn, ggplot, Ploty, geoplotlib.
## Tipos de Gráficos
#### Elementos Gráficos
- Cores 
- Tamanhos e Alinhamentos
- Inclinações e Ângulos
- Áreas e Volumes
**Dicas Gerais:**
	-> Intuitivos
	-> De fácil visualização
	-> Sem confusão (embolamentos,  cores confusas).
	**Obs:** são as mesmas de uma apresentação de Power Point.
#### Elementos Importantes
- Título Geral
- Título nos Eixos
- Legenda
- Legibilidade
- Escalas Intuitivas
#### Qual gráfico escolher?
- Distribuição
- Relacionamento
- Comparação
- Composição
- Localização
- Conexão
- **Depois dar uma olhada em cada um individualmente**.
#### Ballroom Style vs Conference Style
- **Ballroom**
	Information/Entertaining/Impress
	Information Flow: one way
	Large audiences
- **Conference**
	Engage/Persuade/Conclusion/Drive to Action
	Information Flow: two-way/more interactive
	More selective audiences
##### Taxonomia dos Gráficos
- Distribuição, Conexão...
#### Power BI
- Microsoft Power BI (versões web, desktop, mobile)
- Google Data Studio (infográficos)
- Gapminder (crie animações com dados)
- Tableau (Clique e arraste ou SQL)
- QlikView, RStudio, Visual.ly, Tangle, iCharts
- SmartData