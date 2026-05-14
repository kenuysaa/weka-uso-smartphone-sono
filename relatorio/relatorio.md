# Classificação da Qualidade do Sono com Base no Uso Excessivo de Smartphones Utilizando Weka

## 1 Introdução
O uso excessivo de smartphones tornou-se um dos principais fatores associados a alterações nos hábitos de sono da população. O aumento do tempo de exposição às telas, especialmente durante a madrugada, pode impactar negativamente a duração e a qualidade do sono, afetando aspectos físicos, cognitivos e emocionais dos indivíduos.  
Além disso, o crescimento do uso de redes sociais, aplicativos de entretenimento e notificações constantes intensificou comportamentos digitais compulsivos, tornando relevante o estudo da relação entre o uso excessivo de smartphones e problemas relacionados ao sono.  
Nesse contexto, técnicas de Aprendizado de Máquina podem ser utilizadas para identificar padrões comportamentais associados à qualidade do sono, permitindo a construção de modelos capazes de realizar tarefas de classificação com base em dados comportamentais e hábitos digitais.  
Este trabalho propõe a utilização do Weka para desenvolver um experimento de classificação supervisionada voltado à predição da qualidade do sono a partir de um dataset sintético gerado com auxílio de modelos de linguagem (LLMs).  

---
# 2 Objetivos
## 2.1 Objetivo Geral
Investigar o impacto do uso excessivo de smartphones na qualidade do sono por meio da aplicação de técnicas de Classificação aprendizado de máquina.

---
## 2.2 Objetivos Específicos
- Construir um dataset sintético contendo informações comportamentais relacionadas ao uso do celular e à qualidade do sono.
- Realizar análise exploratória e pré-processamento dos dados utilizando os recursos disponíveis no Weka.
- Analisar os resultados obtidos, identificando padrões entre o uso excessivo de smartphones e a qualidade do sono.

---
# 3 Definição do Problema
O problema abordado neste trabalho consiste em classificar a qualidade do sono de usuários de smartphones com base em características relacionadas ao comportamento digital e hábitos de vida.

A tarefa escolhida foi a classificação supervisionada binária.
## 3.1 Entrada
Os atributos de entrada representam características comportamentais dos usuários, como:
- tempo de uso diário do smartphone;
- uso durante a madrugada;
- horas de sono;
- nível de estresse;
- notificações diárias;
- atividade física;
- tempo em redes sociais.
## 3.2 Saída
A saída esperada corresponde à variável:
```txt
qualidade_sono

com classes:
- bom
- ruim
```

---
## 4 Geração do Dataset Sintético
O dataset foi construído utilizando modelos de linguagem (LLMs), seguindo as exigências do enunciado do trabalho.  
A geração dos dados não foi realizada de forma aleatória. Foram utilizadas regras semânticas e relações probabilísticas coerentes com o domínio do problema.  

| Requisito                        | Situação |
| -------------------------------- | -------- |
| Pelo menos 500 instâncias        | Atendido |
| Pelo menos 5 atributos           | Atendido |
| Presença de atributo irrelevante | Atendido |
| Presença de valores faltantes    | Atendido |
| Presença de ruído                | Atendido |
| Presença de outliers             | Atendido |
O dataset foi construído considerando diferentes perfis sintéticos de usuários:
- usuário saudável;
- estudante universitário;
- heavy user;
- gamer noturno;
- trabalhador corporativo;
- usuário compulsivo de redes sociais.