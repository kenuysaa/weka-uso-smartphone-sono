# Analise Inicial

## Estrutura geral
| Item | Valor |
|---|---|
| Instâncias | 500 |
| Atributos | 17 + 1 classe |

- Tarefa: Classificação de Qualidade de Sono (Classe `qualidade_sono`)

## Estatisticas dos Atributos
|Atributo|Tipo|Valores Faltantes(%)|Observação|
|--------|----|--------------------|----------|
|tempo_redes_sociais|numerico|7.2%||
|horas_sono|numerico|7.6%||
|atividade_fisica|binario|5.8%||
|notificacoes_diarias|numerico|6.8%||

## Perfis comportamentais
Os 6 perfis influenciam **simultaneamente** múltiplos atributos com distribuições probabilísticas distintas:

| Perfil | Peso | Características dominantes |
|---|---|---|
| Saudável | 18% | Baixo uso, sono regular, ativo fisicamente |
| Estudante universitário | 18% | Uso moderado-alto, estresse elevado, sono irregular |
| Heavy user | 15% | Uso extremo (>9h), muitas notificações, alta insônia |
| Gamer noturno | 14% | Uso madrugada >80%, luminosidade alta, sono curto |
| Corporativo | 18% | Estresse alto, muitas notificações, uso produtivo |
| Compulsivo de redes | 17% | RS >5h/dia, notificações >250, sono degradado |

## Hipóteses e Problemas Identificados
- **Ruídos** (`<8%`): idades inválidas (−5, 150), `horas_sono` negativas, `notificacoes_diarias` negativas, `horas_uso_diario` > 28h
- **Outliers plausíveis** (`~4%`): `horas_uso=20`, `horas_sono=0`, `tempo_redes_sociais=18`, `notificacoes=1200`, `despertares=15`
- Inconsistências: 
- Hipótese: 
