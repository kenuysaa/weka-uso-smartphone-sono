Para este estudo, a metodologia adotada baseou-se no processo de Knowledge Discovery in Databases (KDD), conforme descrito por Skubisz Neto (2019), visando analisar a relação entre o uso excessivo de smartphone e a qualidade do sono. O fluxo metodológico compreendeu três etapas principais: pré-processamento, mineração de dados e pós-processamento, com documentação detalhada das decisões adotadas em cada fase.

## 1. Pré-processamento

O pré-processamento dos dados consistiu na preparação e limpeza do dataset sintético criado para o estudo. As etapas realizadas incluem:

### Tratamento de valores ausentes:
Valores faltantes foram identificados e tratados por meio de imputação baseada na média para variáveis numéricas e modo para variáveis categóricas, garantindo que inconsistências não prejudicassem a análise posterior.

### Análise de outliers:
Observou-se a presença de casos extremos, como uso de smartphone superior a 12 horas/dia. Esses outliers foram mantidos quando plausíveis, considerando que representam cenários realistas de uso intenso, mas foram ajustados quando inconsistentes, de modo a não distorcer os resultados dos algoritmos.

### Normalização e codificação:
Variáveis numéricas, como smartphone_use_hours e screen_time_before_bed, foram normalizadas para padronizar escalas e melhorar o desempenho de modelos como SVM. Variáveis categóricas, como gender e daily_activity_level, foram codificadas como nominais, compatíveis com o formato ARFF do Weka.

### Aplicação de filtros do Weka:
Foram aplicados filtros que não foram explorados em sala, como o Discretize (para categorizar variáveis contínuas) e RemoveUseless (para eliminar atributos sem relevância estatística). A escolha desses filtros visou enriquecer a representação dos dados e reduzir ruídos, alinhando-se à abordagem proposta por Skubisz Neto (2019).

## 2. Mineração de Dados
Após o pré-processamento, os dados foram submetidos à mineração no software Weka 3.8.1, seguindo as recomendações de Skubisz Neto (2019):

### Definição da variável alvo:
A variável sleep_quality foi definida como atributo meta, com classes "good" e "poor", simulando a presença ou ausência de distúrbios do sono.
### Divisão treino-teste:
Foi adotada a estratégia de validação cruzada em 10 folds, permitindo uma avaliação robusta e reduzindo o viés decorrente da divisão aleatória dos dados.
### Aplicação de algoritmos preditivos:
Árvore de decisão J48: identificou padrões de relação entre uso de smartphone, hábitos noturnos e qualidade do sono, fornecendo regras interpretáveis.
Regressão logística: estimou probabilidades associadas à ocorrência de distúrbios do sono, permitindo avaliação do impacto relativo de cada variável independente.
### Avaliação dos modelos:
Foram analisadas métricas como acurácia, precision, recall, F-measure, kappa statistic e matriz de confusão, permitindo interpretação detalhada do desempenho preditivo. Observou-se, por exemplo, que variáveis relacionadas a hábitos noturnos e tempo de uso de smartphone apresentaram maior capacidade preditiva.
## 3. Visualização e pós-processamento

As visualizações geradas no Weka, como gráficos de distribuição, boxplots e histogramas, serviram para:
- Identificar padrões de uso e agrupamentos de dados;
- Avaliar a separação das classes da variável alvo;
- Suportar a interpretação dos resultados obtidos pelas árvores de decisão e regressão logística.

O pós-processamento consistiu na análise crítica dos padrões extraídos, comparando os achados com a literatura, especialmente o estudo de Skubisz Neto (2019), que destacou fatores organizacionais e psicológicos como preditores relevantes de distúrbios do sono.
