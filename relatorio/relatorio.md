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

![[metodologia]]

---

## 4.2 Pré-processamento

A fase de pré-processamento teve como objetivo garantir a qualidade dos dados antes da mineração.

### Procedimentos realizados:

- Verificação de valores ausentes;
- Padronização de categorias;
- Análise de consistência;
- Verificação de faixas numéricas;
- Identificação de outliers.

---

## 4.3 Análise Exploratória

A análise exploratória permitiu observar padrões iniciais entre os atributos.

### Observações iniciais:

- Usuários com maior tempo de uso noturno apresentaram maior incidência de insônia;
- Altos níveis de notificações diárias mostraram possível relação com baixa qualidade do sono;
- A distribuição dos dados apresentou alguns valores extremos.

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