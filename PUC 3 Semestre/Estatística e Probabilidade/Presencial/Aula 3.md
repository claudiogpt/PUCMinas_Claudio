Na estatística, o uso de \(x^2\) em vez do módulo \(|x|\) para anular negativos tem algumas razões fundamentais, relacionadas a propriedades matemáticas e à facilidade de manipulação.
### 1. **Diferenciabilidade e Suavidade:**
   - A função \(x^2\) é uma função suave (diferenciável) em todo o seu domínio, o que significa que ela possui uma derivada contínua. Isso facilita muito o trabalho analítico, especialmente quando se trata de otimização, cálculo de médias (como na variância) ou derivadas.
   - O módulo \(|x|\), por outro lado, não é diferenciável em \(x = 0\), o que pode complicar a análise, principalmente em contextos que requerem cálculos de derivadas, como otimização.
### 2. **Trabalho com Somatórios:**
   - Ao trabalhar com somatórios, como na variância \(\sigma^2 = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2\), o uso de \(x^2\) torna a manipulação algébrica direta e linear.
   - O módulo \(|x|\) não é tão fácil de manipular em somatórios e pode levar a expressões mais complicadas.
### 3. **Consistência na Escala:**
   - \(x^2\) preserva a escala dos dados de forma mais consistente, já que a quadratura (elevar ao quadrado) amplifica as diferenças, enquanto o módulo apenas transforma os negativos em positivos. Isso é importante para medidas como a variância, que quantificam a dispersão dos dados ao redor da média.
### 4. **Trabalho com Distribuições:**
   - Muitas distribuições estatísticas, como a distribuição normal, têm propriedades que se integram naturalmente ao uso de quadrados. Isso torna as técnicas de inferência e análise mais consistentes e robustas.
### Exemplo Prático:
- **Erro Quadrático Médio (MSE):**
  - Em aprendizagem de máquina, o MSE (\( \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 \)) é uma métrica comum para medir a diferença entre valores observados e preditos. O uso de quadrados torna a função objetivo suave e diferenciável, facilitando a otimização.

Essas propriedades tornam \(x^2\) mais conveniente e robusto em contextos estatísticos e matemáticos em comparação ao uso do módulo \(|x|\).