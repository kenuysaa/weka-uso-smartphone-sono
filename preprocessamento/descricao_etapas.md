# Descrição das Etapas de Pré-processamento

Após a análise inicial, executamos as seguintes ações técnicas na aba **Preprocess** do Weka para refinar o dataset.

## 1. Limpeza de Dados
* **Remoção de Irrelevantes:** Utilizamos o filtro `unsupervised.attribute.Remove` para excluir o atributo `modelo_dispositivo`. Por ser um dado nominal sem correlação estatística direta com a saúde do usuário, sua permanência apenas causaria ruído.
* **Tratamento de Nulos:** Aplicamos o filtro `ReplaceMissingValues`. Isso substituiu os buracos no dataset pela média (no caso de números) ou pela moda (no caso de categorias), mantendo as 500 instâncias originais.

## 2. Transformação de Atributos
* **Normalização:** Utilizamos o filtro `Normalize` em todos os atributos numéricos. Isso colocou valores como `notificacoes_diarias` (escala alta) e `horas_sono` (escala baixa) no mesmo intervalo de [0,1], evitando que o modelo desse peso injusto a números maiores.
* **Discretização:** Para facilitar a análise de grupos, o atributo `idade` foi transformado de numérico para nominal (categorias de faixas etárias) usando o filtro `Discretize`.

## 3. Tratamento Avançado (Filtro Extra)
* **Filtro:** `unsupervised.attribute.InterquartileRange`.
* **Justificativa:** Este filtro foi escolhido para automatizar a detecção de outliers. Ele cria atributos que marcam instâncias com valores "extremos" (ex: uso de smartphone por 22 horas seguidas). Após a identificação, essas instâncias foram analisadas e removidas quando caracterizadas como erros de geração do dado sintético.

## 4. Resultado Final
Após o pré-processamento, o dataset resultou em uma base de dados limpa, normalizada e pronta para a etapa de classificação, garantindo maior estabilidade para os algoritmos de árvore de decisão ou KNN.