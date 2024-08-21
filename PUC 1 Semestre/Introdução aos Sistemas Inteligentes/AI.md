### Paradigmas
- Pensando e agindo humanamente.
	Tentamos modelar a inteligência artificial a partir da humana, imitando nossa capacidade de solução de problemas racionais.
- Pensando e agindo racionalmente.
	Começamos a modelar a AI para resolver problemas de maneira otima, independente dos meios tidos para isso serem ou não similares aos seres humanos.
#### Agindo Racionalmente
- **Racional(neste contexto):** age de forma a alcançar o melhor resultado possível dadas as suas limitações de conhecimento do mundo e sua habilidade de atuação.  
- Esse tipo de comportamento autônomo também é esperado das máquinas que agem racionalmente. Nesse caso, o processo de tomada de decisão não precisa parecer em nada com o processo mental humano, mas o resultado deve fazer sentido dentro de uma medida de utilidade esperada da ação
##### Agente
$$Agente=Arquitetura\;\;+\;\;Programa$$
- Entidade -> percebe o ambiente através de sensores e interage com o ambiente através de atuadores.
- **Arquitetura:** sensores e atuadores.
- **Programa:** raciocínio para tomada de decisões.
$$f = P^{*} -> A$$
**Exemplo:** robôs em marte são independentes, o tempo de transmissão é muito alto entre eles e a terra.
**Sistema de Regras:** 
	Árvore, fluxograma que orienta o agente para um conjunto limitado de regras.
##### Agente Reativo Simples
- **Conceito:** Seleciona ações com base na percepção atual, ignorando o restante do histórico de percepções. **Ex:** aspirador de pó.
- **Características**
	- Utiliza regras de condição ação  
	    **_if_ _X_ _then_ _Y_**
	- Depende apenas da percepção atual.
##### Agente Reativo Baseado em Modelos
**Conceito**: Um agente reativo baseado em modelos possui um estado interno, que dependa do histórico de percepções (modelo do mundo).
**Características**
- Possui um modelo de como o mundo funciona que evolui sem o agente.
	Esse modelo é probabilístico
- Possui um modelo de como as suas ações podem afetar o mundo.
- Mistura a percepção atual com o modelo antes de agir.
- Pode utilizar histórico de percepções para "compreender" como o mundo evolui.
##### Agente Baseado em Objetivos
**Conceito**: Um agente reativo baseado em objetivos busca ações que alcancem seus objetivos
**Características**
- Possui um modelo de como o mundo funciona que evolui sem o agente.
- Possui um modelo de como as suas ações podem afetar o mundo
- Utiliza objetivos, ao invés de regras de condição-ação, para escolher uma ação **_que o leve na direção de seu objetivo_**.
	Ignora métricas não correlatas com o objetivo.
- Um objetivo então poderá ser definido como sendo um estado do ambiente que se deseja alcançar - 'screeshot' do mundo.
##### Agente Baseado na Utilidade
**Conceito**: Um agente reativo baseado na utilidade busca ações que alcancem um maior grau de felicidade para o agente.
**Características**
- Utiliza uma medida de desempenho (utilidade) ao invés de objetivos que permitem apenas uma distinção binária.
- Ao contrário do objetivo, uma medida de utilidade não precisa estar relacionado com um estado final do ambiente, mas com uma **_medida de desempenho do agente_**.
	'Não sabemos onde queremos chegar',
	Bom para 'análise exploratória', consegue descobrir novos caminhos.
- Exemplos incluem: um carro autônomo pode definir como medida de performance o tempo, a distância, ou medidas mais abstratas como menor consumo de combustível. Dessa forma, o carro autônomo irá escolher a ação que irá maximizar a medida de utilidade desejada.
	- **Será que ele consegue ter várias métricas de performance com pesos relativos e correlacionados, definidas ou não pelo ser humano?**
		- A idéia é: ele não precisa necessariamente maximizar, ele pode levar várias medidas correlatas em contas, com pesos diferentes (auto-ajustáveis ou heteroajustáveis).
##### Agente com Aprendizagem
**Conceito**: Um agente com aprendizagem pode ser dividido em quatro componentes:
- **Elemento de Aprendizado**: responsável pelo aperfeiçoamento do elemento de desempenho. 
- **Elemento de Desempenho**: qualquer um dos outros tipos de agente completo que se deseja ajustar.
- **Crítico**: indica para o elemento de aprendizado se o agente está obtendo sucesso, baseado em um padrão de desempenho.
- **Gerador de Problemas**: sugerir ações que levaram a experiências novas e informativas (explorar novas possibilidades).

Por exemplo, um agente baseado em modelos pode ajustar gradativamente o modelo que ele tem do mundo na medida em que vai explorando o ambiente.
##### Modelo Multi-Agente
- Podem coordenar suas ações, não agem de forma isolada (mesmo que hajam de forma independente).
- Tentam atingir um objetivo em conjunto.
##### Exemplo Pac Man
Máquina de estados finitos(3):
- Movimento Aleatório,
- Foge,
- Persegue.
###### Aprendizado em Jogos
- Objeto dela em jogos é melhorar a experiência dos jogadores (ou ajudarem-nos a se desenvolverem) tornando os agentes adaptáveis ao nível dos jogadores. 
**Por Reforço**
- **Dinamic Scripting:** 
	O combate com o computador faz ele adaptar o peso das regras na base e gerar o script com peso personalizado para o jogador.
#### Na música
**MIR - Music Information Retrieval**
	Cria relacionamento entre músicas baseado em informações e regras internas do sistema para recomendá-las (playlist ou próxima música).
**Sistemas de Reconhecimento:**
	Deep Learning, classificação, etc.
	**Query by "Hamming" (Pesquisa por balbúcia)**
		Midomi - tentar reconhecer bandas cover, balbúcias de indivíduos, etc.
**Outras aplicações:**
	Análise,
	Criação de instrumentos e controladores para jogos,
	Composição,
	Performance,
	Processamento de som,
	Streaming, curadoria e recomendação.
### Lógica
- Começada em Aristóteles.
- Tentativa de modelar o conhecimento humano.
**McCarthey:**
	Cientista da área que deu ênfase na modelagem do raciocínio;
	Desenvolver a linguagem Lisp, para lidar com isso.
## Rede Semântica
- Grapho -> contendo relações lógicas entre categorias.
### Na Saúde
- Conseguem reconhecer doenças assintomáticas.
- Conseguem reconhecer doenças com baixa taxa de incidência(podem ser treinados para isso).
- Monitoramento constante da saúde dos indivíduos, alertas perante oscilações para soluções de problemas que os indivíduos tem. (futurista, mas já há implementações, como o GAIMIN).
- Vigilância epidemiológica (controlada por inteligências artificiais).
**PathAi:** 
	Utilizar de visão computacional para descoberta de patologias, como câncer em exames.
**Buoy Health**
	Chatbot + sistema de diagnóstico;
	Sugerir cuidados, orientar para cuidados médicos;
	Versão paga te da acesso a exames laboratoriais.
	Sistemas baseados em regras para diagnósticos.
### Bolsa de Valores
- Para um modelo ser treinado, nos dias atuais, é necessário ter um padrão. 
- Existe padrão no mercado financeiro?
**Duas Estratégias**
- Buy and hold (**análise fundamentalista**);
- Day Trader, Short Trades - comprar e vender (**análise técnica**).
	estatisticamente é uma estratégia perdedora.
**Robôs Para Compra e Venda de Ativos**
- Agilizam no processo de negociação;
	possível fazer de forma paralela;
- São configurados a partir de estratégias definidas;
	Sistemas baseados em regras;
- Baixo custo;
- Exigem a confiança humana.
##### Análise de Risco
- Qual o risco de crédito associado a um cliente? Modelos de classificação.
### Aviação
**Onde são usados modelos:**
- Custos de operação,
	Redução do consumo por otimização de rota.
- **Atrasos e cancelamentos:**
	Empresas estão sujeitas a penalidades,
	**Estratégia:** prevenir ao máximo os atrasos e cancelamentos através de sistemas auxiliares.
- Conforto e atendimento,
- Segurança.
	**Prevenção:**
		Análise de dados de voos,
		Projeto seguro de espaço aéreo.
	**Correção:**
		Piloto automático avançado.
		Sistema de auxílio a tomada de decisão.
	Auxílio de pouso e decolagem.
##### Futuro dela + Sistemas Inteligentes
- _Free flight_ (Voo Livre);
	Não precisam de autorização de torres por suas conexões.
	Aeronaves totalmente autônomas.
- Tecnologia ADS-B para transmissão de dados.
	Para outras aeronaves e estações em terra.
- Aeronaves autônomas.
### AI no Setor Jurídico
- Machine learning: previsão e classificação.
- Processamento de Linguagem Natural (NLP).
#### NLP para Revisão e Análise de Documentos
- **Reconhecimento:** de conceitos de negócios ocultos em documentos.
- **Identificação:** de relacionamento entre conceitos, empresas, locais e pessoas (rede semântica?).
	Busca em texto de relações e distâncias entre elas.
	**Exemplos:**
		Chamadas telefônicas de uma relação policial.
		Investigação de traição.
- **TAR (technology assisted review) 2.0 baseada em PLN (Processamento de Linguagem Natural).**
	O ser humano faz o tagging dos documentos, que vai aprendendo com o ser humano e ficando melhor com o tempo na classificação de relações.
- **Recomendação:** custodiante.
- **Análise de Sentimento:** conteúdo emocional e intensidade.
**Exemplos:**
	**JP Morgan:** substituiu 360.000 horas de advogados em automações de inteligência artificial, na parte de contratos.
	**Data Driven Legal Pricing**.
**Confiar na AI:**
	Critérios de Confiabilidade:
		Justiça,
			Tratar os seres humanos iguais, independente de raça, cor, gênero, etc...
		Explicabilidade,
			Verbose On ("Pensamento Crítico"),
		Segurança,
			Algoritmo não vai falhar,
		Proteção,
			Invasão e corrupção externas e intencionais,
		Tranparência,
			Entender o funcionamento do algoritmo, oposto da caixa preta.
**Checar:**
	Associação brasileira de LawTechs.
### Jornalismo e AI
- Uma das áreas mais afetadas e modificadas pelo mundo da AI.
**Augmented Reporting(Reportagem Aumentada):**
- **Objetivo:** varre a rede buscando Breaking News
	Provavelmente há analise de sentimento envolvida, análise de sentimento prévia.
### Automação de Processos
- Objetivo é reduzir custo das tarefas do dia a dia.
	- Transcrição,
	- Rotulação de imagens e vídeos,
	- Recomendação de conteúdo.
	- Definição de Pauta (por pesquisa).
### Promessa: Storytelling
- IA pode produzir conteúdo e contar histórias.
- Alguns exemplos:
	- Resumos de partidas de futebol.
	- Alertas de Terremoto.
	- Balanços de empresas.
**NLG - Natural Language Generation**
- Usado no NBA na primeira divisão em 2021.
**Data Driven Journalism**
- Dados nos ajudam a interpretar o mundo sob os vieses mais acertados.
- De forma mais concreta, menos abstrata.
**Data Driven Journalistic Operation**
- Padrões de interesse.
	Baseado em populações, regiões do país, etc.
- Previsão de Engajamento.
	A notícia vai produzir engajamento de seu público?
- Alocação de recursos para coberturas.
	Aumentar o valor da peça jornalística através de tecnologias, dados.
	Jornalismo baseado em bases de dados.
		**Brazilian Journarlistic Research - Journalism vs Algorythms**. - Artigo
## Computação Evolutiva
- Ramo da AI que se utiliza de conceitos evolutivos da biologia para resolverem problemas computacionais.
#### Algumas Técnicas
- Colônia de Formigas,
	**Problemas de otimização como:** 
- Inteligência de Enxames,
- Enxame de partículas,
	Conseguem resolver um problema de forma organizada, por agrupamento.
- Algoritmos Genéticos.
	Inspirados em mecanismos de evolução natural.
		Mutações genéticas podem ocorrer,
		Reprodução,
		As populações mais adaptadas sobrevivem.
	**Conceitos:**
		**População Inicial:** conjunto de soluções,
		**Cromossomo:** (conjunto de características).
		**Fluxograma:**
			Inicializa População Inicial,
			Calcula o Desempenho(Fitness(Seleção)),
			Solução Encontrada? Não -> Seleção, Reprodução, Mutação, Fitness(Seleção).
			Fim
##### Como seria o cruzamento entre machine learning e computação evolutiva?
### Machine Learning
- Computadores aprendem sem programação explícita.
#### Aprendizado Online
- Aprendizado ocorre enquanto o sistema está em funcionamento
	carros autônomos mudando o comportamento durante o andar.
- É desejável que a AI se adapte às circunstâncias
- Pode ser usado quando não se têm dados prévios.
#### Aprendizado OffLine
- Aprendizado acontece em intervalos.
- Geralmente utiliza dados capturados durante o funcionamento do sistema.
- Amplamente utilizado (kaggle, é o mais comum).
### Aprendizado Supervisionado
- Sistema treinado a partir de dados.
- O sistema se adapta pelos exemplos (Dataset, Loss Function),
- Sistema fica dependente das proximidades informacionais do conjunto de dados utilizado no treinamento.
	Capacidade de generalização, mesmo que existente, fica limitada.
**Duas fases:**
- Treinamento,
- Utilização do modelo.
**Cuidados:**
- Neste paradigma o ser humano ainda é crucial, pelas suas limitações. Não é robusto para bases de dados incompletas, defeituosas, ou perguntas mal formuladas.
##### Fluxo dos Sistemas Inteligentes
- Criação de modelos,
	Algoritmo ou modelo matemático
- Uso de modelos,
	Uso de algoritmo de decisão
- Sistemas inteligentes,
	Sistema de detecção de fraudes
# INTELIGÊNCIA ARTIFICIAL NÃO É SÓ SOBRE ESTATÍSTICA, ISSO É UMA VERTENTE, OS MODELOS DE HOJE FUNCIONAM ASSIM, MAS HÁ MUITO MAIS A EXPLORAR.
### Aprendizado Não-Supervisionado
- Quando não temos exemplos, ou bons data-sets,
- Podemos usar feedbacks,
- Aprendizado por reforço.
	Robôs limpadores podem se programar para visitar em menor frequência lugares que acumulam menos sujeira, 
	Quando não conhece um ambiente, recebe feedback e registra na memória.

**Técnicas de Aprendizado:**
- Se resumem em duas frentes, **Computacional** e **Estatística**. Nenhuma delas pode ser negligenciada.
	**Computacional**
		 -> Nesta fase, você define e cria a infraestrutura computacional necessária. Isso inclui configurar seu ambiente de desenvolvimento com as bibliotecas e ferramentas necessárias, como Python, TensorFlow, e scikit-learn.
		 -> Também é o momento de preparar seus dados. Isso envolve a coleta, limpeza e transformação dos dados brutos em um formato adequado para treinar e testar modelos.
	**Estatística**
		-> Na fase estatística, você aplica técnicas estatísticas para entender seus dados. Isso inclui a análise exploratória de dados (EDA) para identificar tendências, outliers e relações entre variáveis.
		-> Em seguida, você seleciona modelos estatísticos apropriados com base na natureza dos dados e do problema em questão. Isso pode envolver regressão linear, árvores de decisão, redes neurais, entre outros.
		-> Depois de escolher um modelo, é importante treiná-lo usando seus dados de treinamento e avaliá-lo usando métricas estatísticas relevantes, como precisão, recall ou F1-score.
#### Criação e Uso da Inteligência Artificial
**Fluxo:**
	Pesquisa empresas universidades,
		Usualmente produzem conhecimento, inovam.
	Google, IBM, Microsoft...
		Geralmente desenvolvem a pesquisa anteriormente feita pelas universidades.
	Empresas, Startups, Governo.
		Aí já é mais generalizado, foi começado por uma empresa grande, escalou, e todos os pequenos são capazes de consumir e produzir.

**API - Application Programming Interface**
- Chave na democratização da AI,
- Interconexão de micro-serviços,
- Pago pelo uso (geralmente).
**Exemplos:**
- Endereço a partir do CEP, e o inverso,
- Cotação de moedas,
- Consulta de informações sobre voos,
- Previsão do tempo,
**Aplicações AI:**
	Identificação de sentimentos em fotos e vídeos,
	Perfil psicológico em textos,
	Reconhecimento de Faces, Objetos, Famosos.
	Tradução.

### Inteligência Artificial na Sociedade
**Perigos:**
- Yolu - melhor ferramenta para reconhecimento de objetos através de visão computacional.
	Foi utilizada na guerra, a despeito da vontade de seu criador.
		Criador aposentou devido a tristeza extrema.

**IA pode Criar Erros Ocultos:**
- São visões estatísticas do mundo (os modelos atuais), portanto imperfeitos (aprendizado estatístico é imperfeito).
	**Hipótese:** Estatística não modela muito bem ambiguidade (será?).
- Os modelos frequentemente são caixas pretas, podendo manter ocultos vários erros.
- **Exemplos:**
	Chatbots racistas,
		Que aprendem comportamentos negativos com os indivíduos, 
		Ferem indivíduos.
	Dilemas éticos de veículos autônomos.

**IA Pode Gerar Perda de Habilidades e Pensamento Crítico**
- Motoristas perdendo habilidade de se deslocar no ambiente humano,
- Algoritmos de recomendação influenciando e diminuindo nossa capacidade de tomada de decisão,
- Analistas econômicos se tornando dependentes de AI para tomada de decisões.
 
**Veredito Pessoal:** o problema principal é a confiança excessiva e desmedida no sistema, é a ausência da vida e do trabalho com o qual você se envolve (quiet quitting).
	"Os robôs fazem tudo, não tenho que fazer nada".
	
**Nota:** Enxergo isso como natural, afinal: "reliable systems" nos tornam dependentes, facilitam nossas vidas, dessa forma nos acostumamos a depender do que se torna confiável, adaptando nossas habilidades aos novos meios de vida.

 **Manipulação de Algoritmos de AI Críticos**
- Tomam milhares de decisões cruciais por dia,
- Podem ser explorados para manipular feeds de notícias de redes sociais (que modulam o comportamento de grande parte da sociedade hoje),
	Como já foi feito em eleições políticas,
	Formas de manipulação da sociedade em massa,
- Máquinas de busca podem ser adulteradas para privilegiar certos fornecedores,
- Os hackers estão apenas começando.
	**Inovação no crime**: sistema capazes de hackear o teclado pelo som, roubando informações cruciais.

**AI pode institucionalizar Viéses**
- Vários modelos treinados a partir de bancos de dados, limitados;
- Vieses contidos nos dados podem ser aprendidos pelos modelos de IA;
	**Ex:** 
		**Modelo RH:** em vagas de medicina ou engenharia só indicar homens. Mulher só enfermeira e psicóloga. (Viés de gênero).
- Viés não precisa ser tão óbvio para causar danos;
- Em análises de consumidores os algoritmos podem (e provavelmente vão) fortalecer certos grupos.
	**Ex:** fábrica de móveis só indicava os melhores móveis para pessoas mais prováveis de adquirí-los. (Éticamente ambíguo, de forma pragmática faz sentido).
- Como incluir pessoas que não estão na base de dados ou não foram servidas por elas.
	**Nome Técnico:** Cold Start.
		O "Cold Start" em sistemas de inteligência artificial refere-se a uma situação em que um modelo ou sistema enfrenta desafios significativos devido à falta de dados iniciais ou informações prévias.
	**Obs:** 
		Essa pergunta pode ser ampliada para: Como trabalhar com bases de dados pequenas, raras ou "insignificantes"(estatisticamente).

**AI pode causar perda de empatia:**
- Substituindo o ser humano na interação com o consumidor,
- A empresa perde a habilidade humana de 'ouvir' (mas pode incorporar dados, analisados por alguém, é uma mudança de formato).
	Dificuldade de incorporar dados não inclusos no script (normalização excessiva, dificuldade de inovar, de perceber coisas novas, fora do escopo inicial). Excesso de planejamento.
- Quando você abusa de ChatBots a empresa pode ficar inacessível, e problemas fáceis de resolver podem se tornar difíceis, ou problemas mais difíceis impossíveis.
	Cemig, Oi...

**AI pode causar perda de controle:**
- Decisões difíceis de serem tomadas,
- O julgamento feito pela AI pode causar danos,
**Exemplo:**
	Drones bombardeiam alvo sem questionar;
		Nesse caso o soldado "perfeito" incapaz de desobedecer ordens dadas novas circunstâncias,
	 Um carro autônomo pode intencionalmente tirar uma vida para salvar outra?
		 Talvez a melhor solução ia ser causar dano a si mesmo, seus mecanismos de proteção são melhores que do pedestre.

**IA pode ter implicações sociais muito além do seu negócio**
- Assistentes pessoais com crianças podem moldar a maneira como elas se comunicam com o mundo, apesar de serem excelentes para um adulto já formado.
	Criança pode começar a interagir com o agente quando você não está em casa (mesmo problema do livre acesso da internet para crianças, só que em uma nova geração),
	Agentes aprendem vieses culturais também, não somente os positivos.

**Reestruturação dos papéis de consumidores e empregados**
- Robôs estão substituindo vários trabalhadores, causando transformações,
	**Ex:** Moxy - robô assistente que substitui enfermeiras no texas.
- Transição de papéis de homens por máquinas deveriam (idealmente) garantir que as pessoas tenham oportunidade de adaptação.
	Vai haver expansão dos empregos
		**Dificuldade:** treinamento do pessoal para se adaptarem a esses novos empregos, capacitação, educação.

**Ai vs Segurança e Privacidade dos Dados**
- A tecnologia irá moldar como os consumidores acessam informação, interagem com dispositivos e compartilham informações pessoais. Mas as empresas ainda são responsáveis pela segurança e privacidade desses dados.
	**Ex:** empresa que monitora a saúde dos indivíduos de forma geral as vendendo para seguradoras de saúde. 
		Esses dados podem ser corrompidos -> não há controle do uso do bracelete ou honestidade / guidelines no uso desses dados.

**Responsabilidade / O que fazer a respeito?**
- Algoritmos importantes (no estado atual das coisas, no nível mundial de abstração) devem ter gerentes de projetos para avaliar decisões e monitorá-los.
- Como o algoritmo trabalha os princípios chave da sua organização e da nossa sociedade?
	**Ex:** interação de mídias com crianças.
- Quem irá garantir a segurança do algoritmo?
	**Ex:** hackers conseguem manipular, qual seria o dano causado?
- Quem é afetado pelo algoritmo, essas populações estão sendo consideradas?
	**Ex:** os vieses podem ser de difícil acesso, as pesquisas devem continuar.
- Quem irá operar os algoritmos, com qual objetivo?

**Alertas Extras Sobre o Uso da AI**
-   Algoritmos são normalmente implementados sem uma forma de se considerar problemas. Ou seja, se você se considerar um "injustiçado" por uma tomada de decisão automatizada por um sistema inteligência, provavelmente você não terá como apelar da decisão e apontar os problemas com o processo de raciocínio do algoritmo. 
	-> As pessoas tendem a considerar as decisões tomadas por algoritmos mais objetivas e confiáveis, que as decisões humanas, o que torna mais difícil recorrer de uma decisão.
	-> "Caixas pretas" também dificultam o processo.
-    A IA torna fácil não nos sentirmos responsáveis. Desenvolvedores acusam as fontes de informação quando o programa vai mal, enquanto os clientes e especialistas acusam os desenvolvedores de um algoritmo mal projetado.
	-> No final, ninguém se sente responsável pelo problema e ninguém toma medidas para mitigá-lo.
-     **A IA codifica e magnifica vieses.** Isso significa que a IA não apenas representa os preconceitos preexistentes na nossa sociedade, mas que ela pode ser responsável por amplificá-lo:
	**Ex:** Se um algoritmo envia mais policiais para uma região socialmente vulnerável, por considerá-la mais perigosa, este excesso de policiais irão realizar mais prisões, o que fará com que o algoritmo considere a região ainda mais perigosa, e envie mais policiais para lá **dados corrompidos pela ação do agente de inteligência artificial**, exemplo de contaminação do "sample". Este loop amplifica a distorção social já existente. Um outro exemplo apresentado por Rachel Thomas é o fato dos algoritmos de visão computacional obterem piores resultados com pessoas de cor. Veja a figura a seguir.
-     Otimizar métricas acima de tudo leva a resultados negativos (as vezes catastróficos).
	 **Ex:** algoritmos de recomendação que indicam vídeos ou posts, tentando maximizar o tempo que o usuário consome na plataforma pode indicar material de conteúdo duvidoso, ou mesmo _fake news_, desde que o assunto seja adequado ao perfil de usuário definido pelo algoritmo. Uma pessoa com ideias facistas, por exemplo, iria receber uma enxurrada de vídeos e posts racistas, incentivando ainda mais a radicalização desta pessoa. 
		 **O Dilema das Redes**.
-     As grandes corporações de tecnologia - _Tech Giants_ - não são responsabilizadas. 
	**Ex:** Como no caso das eleições Americanas ou o Genocídio em Mianmar. São necessários marcos regulatórios mais amplos e específicos para atacar estes problemas e fazer com que as companhias paguem por seus erros.

**Cuidados com Sistemas Inteligentes**
- Explainability,
- Sistemas de appeal (recorrer a decisões),
- Possíveis de verificar e alterar,
- Passíveis de questionamento e verificação.
- Algoritmos devem ser desenhados para todos, soluções em massa privilegiam aqueles que não tem dinheiro ou condições,
	Ricos frequentemente ainda tem acesso a cuidado humano (mais caro e difícil).
- Os sistemas inteligentes hoje estão estendendo a burocracia, que pode ser usada para fugir das responsabilidades.
	Cemig e OI.
- Análise correta dos dados, um sistema inteligente pode prejudicar alguém que faz um bom trabalho pelo fato de outras pessoas adulterarem as métricas.
	Quando métricas se tornam muito importantes (especialmente métricas errôneas, não descritivas) surgem mercados paralelos de roubo, de adulteração das métricas para se obter vantagens.

**Runaway Feedback Loops**
- Falha de update no sistema:
	- É uma falha de update nos feedback loops, fazendo com que a ação do sistema faça com que o círculo de feedback seja aumentado de forma desproporcional.
	- Decisions made by the system influence the data that is fed to it in the future (how to acess if this is correct or even makes sense?).