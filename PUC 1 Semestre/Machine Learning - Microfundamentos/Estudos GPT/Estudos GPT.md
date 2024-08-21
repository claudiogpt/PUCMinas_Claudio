### Média dos Cross Validation Scores
- Checar se o modelo generaliza bem para novos dados
- Existem graus de overfitting
	- As vezes o modelo funciona melhor para  certo tipo de dado ou alvo
	- Dessa forma você checar a performance geral dos modelos em diferentes tipos de dados ou alvos
### Principal Component Analysis
- **Objetivo**
	- Manter a variância alta diminuindo a dimensionalidade dos dados.
		- Menos dados suficientemente diferentes entre si.
###### Por que Variância = Informação?
1. **Discriminação**: Alta variância ajuda a discriminar entre diferentes classes ou categorias.
2. **Robustez**: Componentes com alta variância são geralmente mais robustos a erros e ruídos.
3. **Interpretabilidade**: Os principais componentes capturam os aspectos mais "importantes" dos dados, tornando mais fácil de interpretar.
##### GridSearchCV e RandomizedSearchCV
- Eles já fazem a validação cruzada e escolhem o melhor modelo baseado nessa métrica.
### XGBoost 
- Muito eficiente, mas funciona melhor com seleção de hiperparâmetros.
### Seleção Computacional de Features
1. **Seleção Unívoca**: Utiliza testes estatísticos como qui-quadrado, ANOVA, correlação.
2. **RFE (Recursive Feature Elimination)**: Elimina recursivamente as features menos importantes.
3. **LASSO (Least Absolute Shrinkage and Selection Operator)**: Regularização L1 que pode zerar pesos, efetivamente eliminando features.
4. **Ridge**: Regularização L2, não elimina mas minimiza o impacto de features irrelevantes.
5. **Tree-based Methods**: Como Random Forest ou árvores de decisão, que oferecem importância de feature.
6. **SFS (Sequential Forward Selection)**: Adiciona uma feature de cada vez baseado no desempenho do modelo.
7. **SBS (Sequential Backward Selection)**: Remove uma feature de cada vez.
8. **mRMR (Minimum Redundancy Maximum Relevance)**: Minimiza redundância e maximiza relevância.
9. **Correlation Matrix with Heatmap**: Elimina features altamente correlacionadas.
10. **t-SNE (t-Distributed Stochastic Neighbor Embedding)**: Técnica de redução de dimensionalidade mais sofisticada que o PCA.
11. **UMAP (Uniform Manifold Approximation and Projection)**: Também para redução de dimensionalidade, mais rápido que t-SNE.
12. **Autoencoders**: Redes neurais para redução de dimensionalidade.

`