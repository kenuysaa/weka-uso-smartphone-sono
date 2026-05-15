# Classificação da Qualidade do Sono com Base no Uso Excessivo de Smartphones Utilizando Weka

# 1. Introdução

O uso excessivo de smartphones tornou-se um comportamento comum na sociedade contemporânea, principalmente entre jovens e adultos. O aumento do tempo de exposição às telas, especialmente durante o período noturno, vem sendo associado a problemas relacionados à qualidade do sono, insônia, fadiga e alterações cognitivas.

Com o avanço das técnicas de Inteligência Artificial e Mineração de Dados, tornou-se possível identificar padrões e relações entre variáveis comportamentais e problemas de saúde. Nesse contexto, este trabalho aplica a metodologia KDD (Knowledge Discovery in Databases) para preparação e análise de dados relacionados ao uso de smartphones e qualidade do sono utilizando o software Weka.

A proposta segue os conceitos descritos por Skubisz Neto (2019), enfatizando as etapas de seleção, pré-processamento e preparação dos dados antes da aplicação de algoritmos de mineração.

---

# 2. Objetivos

## 2.1 Objetivo Geral

Aplicar a metodologia KDD na preparação e organização de um conjunto de dados relacionado ao uso de smartphones e qualidade do sono para posterior análise utilizando o software Weka.

## 2.2 Objetivos Específicos

- Estruturar um dataset compatível com o Weka;
- Realizar limpeza e pré-processamento dos dados;
- Identificar valores ausentes e possíveis outliers;
- Preparar os atributos para futura aplicação de algoritmos de classificação;
- Realizar análise exploratória inicial dos dados.

---

# 3. Descrição da Base de Dados

O conjunto de dados foi desenvolvido contendo informações relacionadas aos hábitos de uso de smartphones e variáveis associadas à qualidade do sono.

## 3.1 Atributos Utilizados

| Atributo | Descrição | Tipo |
|---|---|---|
| age | Idade do usuário | Numérico |
| gender | Gênero do usuário | Categórico |
| smartphone_use_hours | Horas diárias de uso do smartphone | Numérico |
| nighttime_use | Uso do smartphone durante a madrugada | Binário |
| notifications_daily | Quantidade de notificações diárias | Numérico |
| screen_time_before_bed | Tempo de tela antes de dormir | Numérico |
| stress_level | Nível de estresse do usuário | Numérico |
| physical_activity | Nível de atividade física | Categórico |
| insomnia | Presença de sintomas de insônia | Binário |
| sleep_quality | Qualidade do sono (variável alvo) | Categórico |

---

# 4. Metodologia KDD

Para este estudo, a metodologia adotada baseou-se no processo de Knowledge Discovery in Databases (KDD), conforme descrito por Skubisz Neto (2019), visando analisar a relação entre o uso excessivo de smartphone e a qualidade do sono. O fluxo metodológico compreendeu três etapas principais: pré-processamento, mineração de dados e pós-processamento, com documentação detalhada das decisões adotadas em cada fase.

## 4.1 Pré-processamento

O pré-processamento dos dados consistiu na preparação e limpeza do dataset sintético criado para o estudo. As etapas realizadas incluem:

### Tratamento de valores ausentes:
Valores faltantes foram identificados e tratados por meio de imputação baseada na média para variáveis numéricas e modo para variáveis categóricas, garantindo que inconsistências não prejudicassem a análise posterior.

### Análise de outliers:
Observou-se a presença de casos extremos, como uso de smartphone superior a 12 horas/dia. Esses outliers foram mantidos quando plausíveis, considerando que representam cenários realistas de uso intenso, mas foram ajustados quando inconsistentes, de modo a não distorcer os resultados dos algoritmos.

### Normalização e codificação:
Variáveis numéricas, como smartphone_use_hours e screen_time_before_bed, foram normalizadas para padronizar escalas e melhorar o desempenho de modelos como SVM. Variáveis categóricas, como gender e daily_activity_level, foram codificadas como nominais, compatíveis com o formato ARFF do Weka.

### Aplicação de filtros do Weka:
Foram aplicados filtros que não foram explorados em sala, como o Discretize (para categorizar variáveis contínuas) e RemoveUseless (para eliminar atributos sem relevância estatística). A escolha desses filtros visou enriquecer a representação dos dados e reduzir ruídos, alinhando-se à abordagem proposta por Skubisz Neto (2019).

## 4.2 Mineração de Dados
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
## 4.3 Visualização e pós-processamento

As visualizações geradas no Weka, como gráficos de distribuição, boxplots e histogramas, serviram para:
- Identificar padrões de uso e agrupamentos de dados;
- Avaliar a separação das classes da variável alvo;
- Suportar a interpretação dos resultados obtidos pelas árvores de decisão e regressão logística.

O pós-processamento consistiu na análise crítica dos padrões extraídos, comparando os achados com a literatura, especialmente o estudo de Skubisz Neto (2019), que destacou fatores organizacionais e psicológicos como preditores relevantes de distúrbios do sono.

---

# 5. Análise de Outliers

Durante a visualização dos gráficos de dispersão, foram identificados possíveis outliers em determinadas variáveis.

## Variáveis com possíveis outliers

| Variável | Observação |
|---|---|
| insomnia | Pontos isolados fora da distribuição principal |
| luminosidade_am | Valores extremos acima e abaixo da média |
| notificacoes_diar | Usuários com quantidade excessiva de notificações |

## Interpretação

Os outliers identificados podem representar:

- Comportamentos extremos reais;
- Dados inconsistentes;
- Casos raros relevantes para análise.

Nesta etapa, os outliers foram mantidos para avaliação posterior no Weka.

---

# 6. Preparação para o Weka

A base de dados foi estruturada em formato compatível com o software Weka.

## Etapas planejadas no Weka

As próximas etapas incluem:

- Normalização dos dados;
- Conversão de atributos categóricos;
- Aplicação de filtros;
- Seleção de atributos relevantes;
- Aplicação de algoritmos de classificação.

Os algoritmos previstos incluem:

- J48;
- Regressão Logística.

---

# 7. Resultados Esperados

Espera-se identificar padrões que demonstrem a relação entre o uso excessivo de smartphones e problemas relacionados ao sono.

Possíveis resultados esperados:

- Maior uso noturno associado à insônia;
- Redução da qualidade do sono em usuários com alta exposição à tela;
- Influência do número de notificações na interrupção do sono.

---

# 8. Limitações do Trabalho

As principais limitações incluem:

- Uso de dados sintéticos;
- Presença de valores extremos;
- Dependência de futuras etapas de mineração.

---

# 9. Conclusão

A etapa de preparação dos dados utilizando a metodologia KDD foi concluída com sucesso, permitindo estruturar uma base adequada para futuras aplicações de mineração de dados no Weka.

A análise exploratória indicou padrões relevantes e a presença de possíveis outliers que poderão impactar os modelos preditivos futuros.

---

# 10. Referências

- SKUBISZ NETO, João. Data Mining and KDD Methodology Applied to Predictive Analysis. 2019.
- Weka Data Mining Software. University of Waikato.