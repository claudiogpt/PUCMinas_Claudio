## AutoML
- Inteligência artificial que constrói modelos de machine learning, de forma autônoma ou apoiando no processo;
- Redução no tempo de criação de modelos de ML;
- Diminui a barra de conhecimento necessário em ML;
### DataScience Report
##### What DScientists spend their time on?
- Building training sets: 3%
- Cleaning and organizing data: 60%
- Collecting data sets: 19%
- Mining Data for Patterns: 9%
- Refining Algos: 4%
- Other: 5%
**OBS:** 80% relacionado a tarefas de pré-processamento
### Principais Etapas
- Feature Selection/Engineering
- Otimização de HiperParâmetros
- Comparação de Modelo
###### Acesso Simplificado
- Amazon SageMaker
- Microsoft Azure AutoML
- Google Cloud AutoML
#### H20.ai
- Lançado em 2012 oferece bibliotecas Open-Source.
- 2017 - DriverLess AI. Adotado em várias indústrias (serviço financeiroo/varejo)
### TPOT (Tree-based Pipeline Optimization Tool)
- Biblioteca python free. 
	- Implementa algoritmo genético para evoluir e identificar modelos. Alcança 97% de precisão com o DataSet IRIS.
	- Basicamente otimização de hiperparâmetros.
- Pode levar horas/dias processando dependendo do escopo/hardware/configuração.
### MLOps
**Contexto**
- **Revolução Industrial:** manufatura automatizada.
- **Sistemas Agile:** operacionalização dos ciclos de vida dos produtos, favorecendo a inovação contínua.
- **Devops:** otimizou ainda mais o ciclo de produção e favoreceu a Big Data.
- **Machine Learning:** chegou a nossa vez.
**Definição**
- Prática de colaboração e comunicação entre cientistas de dados e profissionais de operação.
- Visa auxiliar na gestão do ciclo de vida de processos de Machine Learning.
- Aumento da automação e melhora da qualidade de produção de ML.
**Aplicação**
- Foca nos requisitos do negócio e regulação
- Conjunto de boas práticas - visa eliminar o desperdício e melhorar qualidade
- Deve ser independente de plataforma
- Facilita a reprodutibilidade de Experimentos
- Gestão de Artefatos (Scripts, Bases de Dados, Etc...)
#### Exemplo
**DVC - Data Version Control:**
- Open source Version Control System for Machine Learning: https://dvc.org.br
**O que oferece:**
- Controle de versionamento de projetos
- Gestão de experimentos
- Implantação e colaboração