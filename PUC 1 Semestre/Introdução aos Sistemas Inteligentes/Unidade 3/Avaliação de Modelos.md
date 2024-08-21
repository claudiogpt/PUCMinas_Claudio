## Método Zheng
Dados Históricos -> Protótipo de Modelo -> Avaliação Off-Line(Resultados de validação)
Dados Operacionais -> Protótipo de Modelo -> Avaliação Off-Line(Resultados Operacionais)
Dados Operacionais -> Modelo Final  -> Avaliação On-Line(Resultados Operacionais)
#### Validação Cruzada
$$\frac{1}{5}\sum_{i=1}^{5} Performance$$
- **Ex:** dividido em 5 mini-batches(K-Folds) e treinado cada um separadamente.
	**Performance:** somatório das 5 dividido por elas.

**Parâmetros vs Hiperparâmetros:**
	**Parâmetros de um modelo:** variáveis ajustadas no processo de aprendizado
	**Hiper-parâmetros:** precisam ser ajustados mas não são aprendidos.
		Futuros modelos ou agentes podem ajustar(aprender) hiperparâmetros dado um conjunto de problemas.
**Busca por Hiperparâmetros:**
	_Autotuning_ técnicas para ajustar os Hiperparâmetros buscando maximizar a qualidade de um modelo.
#### Matriz de Confusão
- **Precisão**
	Alta -> Poucos falsos positivos
	Baixa -> Muitos falsos positivos
- **Revocação**
	Alta -> Poucos falsos negativos
	Baixa -> Muitos faltos negativos
**OBS:** geralmente uma é o oposto da outra.
- **F-measure ou F-score**
	média harmônica dos 2$$F = 2\frac{(Precisão)(Revocação)}{Precisão + Revocação}$$
- **Acurácia**
	Porcentagem dos elementos classificados corretamente(positivos ou negativos).
	$$A=\frac{(T_p+T_n)}{(T_p+T_n+F_p+F_n)}$$
	Medida ruim, não mostra onde está o erro. Especialmente ruim para dados desbalanceados.
		Em alguns casos (como fraude) a taxa de ocorrência é baixa, se o modelo chutar sempre negativo ele vai ter um percentual de acerto de 99,9%, mesmo não fazendo nada.
- **Acurácia Média**
	Por classe.