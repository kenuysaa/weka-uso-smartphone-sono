# Analise Inicial
Esta análise inicial tem como objetivo compreender a estrutura geral do dataset sintético desenvolvido para o projeto de classificação da qualidade do sono com base no uso excessivo de smartphones.  
A etapa foi realizada antes de qualquer procedimento de pré-processamento, conforme exigido no enunciado do trabalho, permitindo identificar padrões, inconsistências, valores faltantes, ruídos e possíveis outliers presentes na base de dados.  
Além disso, a análise exploratória inicial auxilia na formulação de hipóteses sobre o comportamento dos atributos e orienta as decisões posteriores de limpeza e transformação dos dados no Weka.
 
 **Visão Geral do Dataset**

| Item                  | Valor                 |
| --------------------- | --------------------- |
| Número de Instâncias  | 500                   |
| Número de Atributos   | 18                    |
| Classe-alvo           | `qualidade_sono`      |
| Tarefa de Aprendizado | Classificação Binária |
**Distribuição das Classes**

| bom | ruim |
| --- | ---- |
| 209 | 291  |

A distribuição das classes mostra um leve desbalanceamento em favor da classe `ruim`, indicando predominância de usuários com padrões associados à pior qualidade do sono.

Esse comportamento é coerente com a proposta do problema, considerando que o dataset foi construído para simular cenários de uso excessivo de smartphones.

---

# 1 Descrição dos Atributos

| Atributo               | Tipo     | Descrição                                             |
| ---------------------- | -------- | ----------------------------------------------------- |
| idade                  | Numérico | Idade do usuário                                      |
| genero                 | Nominal  | Gênero do usuário                                     |
| horas_uso_diario       | Numérico | Tempo total de uso diário do smartphone               |
| tempo_redes_sociais    | Numérico | Tempo diário gasto em redes sociais                   |
| horas_sono             | Numérico | Quantidade média de horas dormidas                    |
| uso_madrugada          | Nominal  | Indica uso do smartphone durante a madrugada          |
| atividade_fisica       | Nominal  | Frequência de atividade física                        |
| ocupacao               | Nominal  | Perfil ocupacional do usuário                         |
| modelo_dispositivo     | Nominal  | Modelo do smartphone utilizado                        |
| nivel_estresse         | Numérico | Escala de estresse do usuário                         |
| consumo_energia        | Numérico | Indicador sintético de consumo energético do aparelho |
| despertares_noturnos   | Numérico | Quantidade de despertares durante o sono              |
| notificacoes_diarias   | Numérico | Quantidade diária de notificações recebidas           |
| luminosidade_ambiente  | Numérico | Intensidade luminosa média do ambiente                |
| insonia                | Nominal  | Indicação de sintomas de insônia                      |
| uso_apps_produtividade | Numérico | Tempo gasto em aplicativos produtivos                 |
| nivel_uso              | Nominal  | Perfil de intensidade de uso do smartphone            |
| qualidade_sono         | Nominal  | Classe-alvo da classificação                          |

---
# 2 Estatísticas Gerais e Problemas Identificados
A análise inicial permitiu identificar diversos comportamentos relevantes no dataset.
## 2.1 Valores Faltantes

| Atributo             | Quantidade de Valores Faltantes |
| -------------------- | ------------------------------- |
| tempo_redes_sociais  | 35                              |
| horas_sono           | 29                              |
| notificacoes_diarias | 40                              |
| atividade_fisica     | 30                              |

Os valores faltantes aparecem em atributos importantes para o problema, principalmente aqueles relacionados diretamente aos hábitos digitais e à qualidade do sono.

Esses valores ausentes foram inseridos propositalmente para simular:

- falhas de sensores;
- perda de coleta;
- formulários incompletos.

---
## 2.2 Inconsistências e Ruídos

| Atributo             | Problema Encontrado                    |
| -------------------- | -------------------------------------- |
| idade                | Valores negativos e extremamente altos |
| horas_sono           | Valores negativos                      |
| despertares_noturnos | Quantidades negativas                  |
| notificacoes_diarias | Valores negativos                      |
| horas_uso_diario     | Valores acima de 24 horas              |

Os ruídos foram inseridos de forma controlada para representar erros de entrada e inconsistências comuns em bases reais.

Exemplos encontrados:
- `idade = -10`
- `idade = 200`
- `horas_sono = -1.4`
- `despertares_noturnos = -3`
- `horas_uso_diario = 30`

---
## 2.3 Outliers
Também foram identificados valores extremos considerados outliers.

| Atributo             | Exemplos de Outliers |
| -------------------- | -------------------- |
| horas_uso_diario     | 25, 28, 30           |
| notificacoes_diarias | 650, 792, 1000, 1200 |
| tempo_redes_sociais  | 17 horas             |
| horas_sono           | 0 horas              |

Diferentemente das inconsistências, alguns desses valores podem representar comportamentos extremos, porém plausíveis, relacionados ao uso compulsivo de smartphones.

---
# 3 Atributos Potencialmente Irrelevantes
Durante a análise inicial, alguns atributos demonstraram baixa relação aparente com a variável-alvo.

| Atributo           | Justificativa                                               |
| ------------------ | ----------------------------------------------------------- |
| modelo_dispositivo | Não possui relação causal direta com a qualidade do sono    |
| consumo_energia    | Pode não contribuir significativamente para a classificação |

Esses atributos poderão ser posteriormente avaliados utilizando filtros de seleção de atributos no Weka.

---
# 4 Relações Observadas Entre os Atributos
A análise exploratória permitiu levantar algumas relações iniciais entre os atributos do dataset e a classe `qualidade_sono`.

| Relação Observada                     | Interpretação Inicial                                    |
| ------------------------------------- | -------------------------------------------------------- |
| horas_uso_diario × qualidade_sono     | Maior uso diário tende a se relacionar com sono ruim     |
| uso_madrugada × qualidade_sono        | Uso durante a madrugada pode prejudicar o sono           |
| horas_sono × qualidade_sono           | Menor duração do sono tende a aumentar a classe ruim     |
| nivel_estresse × qualidade_sono       | Estresse elevado pode impactar negativamente o sono      |
| notificacoes_diarias × qualidade_sono | Muitas notificações podem aumentar interrupções noturnas |

Os resultados indicam que a qualidade do sono depende de múltiplos fatores comportamentais e não apenas de um único atributo isolado.

---
# 5 Hipóteses do Projeto
Com base na análise inicial, foram formuladas as seguintes hipóteses:

| cod | Descrição                                                                                                                    |
| --- | ---------------------------------------------------------------------------------------------------------------------------- |
| **H1**  | Usuários com maior tempo de uso diário do smartphone possuem maior probabilidade de apresentar `qualidade_sono = ruim`.      |
| **H2**  | O uso frequente do smartphone durante a madrugada está associado à pior qualidade do sono.                                   |
| **H3**  | Altos níveis de notificações diárias e estresse tendem a impactar negativamente o sono.                                      |
| **H4**  | A remoção ou tratamento adequado de inconsistências e outliers poderá melhorar o desempenho dos algoritmos de classificação. |
# 6 Conclusão
A análise exploratória inicial mostrou que o dataset possui estrutura adequada para a tarefa de classificação proposta no projeto.
Além disso, foram identificados:
- valores faltantes;
- inconsistências;
- ruídos;
- outliers;
- atributos potencialmente irrelevantes.

Esses elementos foram inseridos propositalmente durante a geração do dataset para permitir análises mais realistas e enriquecer o processo de pré-processamento no Weka.

Os resultados desta etapa servirão como base para as próximas fases do projeto, incluindo limpeza dos dados, transformação, visualização e treinamento dos modelos de aprendizado de máquina.
