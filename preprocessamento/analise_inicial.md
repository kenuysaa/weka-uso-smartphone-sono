# Análise Exploratória Inicial - Qualidade do Sono e Smartphone

## 1. Visão Geral do Dataset (Raw Data)
| Item                  | Valor                                        |
| --------------------- | -------------------------------------------- |
| Número de Instâncias  | 500                                          |
| Número de Atributos   | 18                                           |
| Classe                | qualidade_sono                               |
| Tarefa                | Classificação Binária                        |
| Equilíbrio de Classes | ruim (291 instâncias) e bom (209 instâncias) |

## 2. Estatísticas e Problemas Identificados
Análise técnica das variáveis conforme observado no estado bruto do dataset
| **Atributo**           | **Tipo** | **Problema Identificado** | **Evidência/Estatística**                                                  |
| ---------------------- | -------- | ------------------------- | -------------------------------------------------------------------------- |
| `idade`                | Numérico | Outliers/Ruído            | Presença de valores impossíveis: **-10** e **200** anos.                   |
| `horas_uso_diario`     | Numérico | Outliers                  | Valor máximo de **30 horas**, o que é fisicamente impossível em um dia.    |
| `tempo_redes_sociais`  | Numérico | Valores Faltantes         | 35 instâncias com valor `?`.                                               |
| `horas_sono`           | Numérico | Valores Faltantes/Ruído   | 29 faltantes e valores negativos (**-1.4h**).                              |
| `despertares_noturnos` | Numérico | Inconsistência            | Valor mínimo de **-3**, inconsistente para uma contagem.                   |
| `notificacoes_diarias` | Numérico | Valores Faltantes         | 40 instâncias com valor `?`.                                               |
| `modelo_dispositivo`   | Nominal  | Irrelevante/Faltante      | Atributo com 100% de dados faltantes ou sem nexo causal direto com o sono. |

## 3. Identificação de Elementos Intencionais
O dataset contém os seguintes elementos para tratamento:
- **Atributo Irrelevante:** `modelo_dispositivo` e `consumo_energia` foram identificados como variáveis que não contribuem para a predição da qualidade do sono.
- **Valores Faltantes:** Concentrados em atributos críticos como `tempo_redes_sociais` e `notificacoes_diarias`.
- **Outliers:** Inseridos propositalmente em `idade` (200) e `horas_uso_diario` (30) para testar o rigor do pré-processamento.

## 4. Hipóteses para o Projeto
1. **H1:** Existe uma correlação forte e positiva entre o `uso_madrugada` (binário) e a classe `qualidade_sono = ruim`. 
2. **H2:** O aumento nas `notificacoes_diarias` atua como um fator de ruído que impacta negativamente o tempo de sono profundo.
3. **H3:** A limpeza dos outliers de `idade` e `horas_uso_diario` reduzirá significativamente o erro médio dos algoritmos de classificação.
