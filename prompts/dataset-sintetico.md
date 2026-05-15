Prompt Utilizado para a geração do Dataset: Versão 2.0

## Versão 1.0
Inicialmente foi utilizada o ChatGPT para gerar ideiais de atributos para o Dataset
```
Gere um dataset fictício com 500 usuários de smartphone para prever qualidade do sono. Os atributos devem ser: idade horas_uso_diario tempo_redes_sociais horas_sono uso_madrugada modelo_dispositivo nivel_uso As classes devem ser: bom, ruim. Os dados devem seguir padrões coerentes:

- usuários com muitas horas de uso de celular e pouco sono devem possuir maior chance de sono ruim.
- uso do celular durante madrugada deve aumentar probabilidade de sono ruim.
- atividade física deve estar associada a melhor qualidade de sono. Inclua:
- valores faltantes
- ruídos
- outliers Formato CSV. 
```

## Versão 1.5
Foi atribuido exemplos de ruidos e outliners
```
Gere um dataset fictício com 500 usuários de smartphone para prever qualidade do sono. Os atributos devem ser: idade horas_uso_diario tempo_redes_sociais horas_sono uso_madrugada modelo_dispositivo nivel_uso

As classes devem ser: bom, ruim.

Os dados devem seguir padrões coerentes: * usuários com muitas horas de uso de celular e pouco sono devem possuir maior chance de sono ruim. * uso do celular durante madrugada deve aumentar probabilidade de sono ruim. * atividade física deve estar associada a melhor qualidade de sono. Inclua:

- valores faltantes
- ruídos ex: horas_sono = -3 idade = 150
- outliers ex: | 20 horas de uso por dia | | 0 horas de sono |

Formato CSV.
```
## Versão 2.0
Com auxilio do ChatGPT, fora implementada o seguinte prompit, expecificando melhor cada caracteristica apresentada
```
Gere um dataset sintético em formato [CSV] contendo [500] usuários de smartphone para um experimento de aprendizado de máquina voltado à predição da qualidade do sono. Os dados devem simular comportamentos digitais e hábitos de vida relacionados à qualidade do sono, permitindo treinamento e avaliação de modelos de classificação supervisionada.

ATRIBUTOS:

- idade,
- genero,
- horas_uso_diario,
- tempo_redes_sociais,
- horas_sono,
- uso_madrugada,
- atividade_fisica,
- ocupacao,
- modelo_dispositivo,
- nivel_estresse,
- consumo_energia,
- despertares_noturnos,
- notificacoes_diarias,
- luminosidade_ambiente,
- insonia,
- uso_apps_produtividade,
- nivel_uso

CLASSE:

- qualidade_sono

VALORES DA CLASSE:

- bom,
- ruim

REGRAS SEMÂNTICAS E HIPÓTESES:

1. Usuários com:
    - muitas horas de uso diário,
    - pouco tempo de sono,
    - tempo alto em redes sociais,
    - uso frequente durante a madrugada,
    - alta quantidade de notificações,
    - estresse elevado,
    - insônia, devem possuir maior probabilidade da classe: -> qualidade_sono = ruim
      
2. Usuários com:
    - atividade física moderada ou alta,
    - sono regular,
    - baixo uso noturno,
    - poucas interrupções noturnas,
    - menor tempo em redes sociais, devem possuir maior probabilidade da classe: -> qualidade_sono = bom
      
3. O dataset deve conter diferentes perfis comportamentais sintéticos, por exemplo:
    - usuário saudável
    - estudante universitario
    - heavy user
    - gamer noturno
    - trabalhador corporativo
    - usuário compulsivo de redes sociais
      
4. As distribuições NÃO devem ser uniformes. Gere padrões realistas e heterogêneos.
- uso_madrugada: maior incidência entre usuários com sono ruim
- horas_sono: normalmente entre 4 e 9 horas, mas podendo conter exceções controladas
- horas_uso_diario: normalmente entre 2 e 12 horas

VALORES FALTANTES: Inclua mais de 5% de valores ausentes em atributos:

- tempo_redes_sociais
- horas_sono
- atividade_fisica
- notificacoes_diarias

Os valores faltantes devem simular:

- falhas de sensores
- formulários incompletos
- perda de coleta

INSERÇÃO RUÍDOS: Inclua pequenas quantidades de dados inconsistentes simulando erros de entrada e coleta.

Exemplos de ruídos:

- idade = 150
- idade = -5
- horas_sono = -3
- horas_uso_diario = 30
- notificacoes_diarias = -20
- despertares_noturnos = -1

Esses ruídos devem representar menos de 8% do dataset.

INSERÇÃO CONTROLADA DE OUTLIERS: Inclua usuários extremos, porém plausíveis, para enriquecer análises estatísticas e testes de robustez.

Exemplos de outliers:

- horas_uso_diario = 20
- horas_sono = 0
- tempo_redes_sociais = 18
- notificacoes_diarias = 1200
- despertares_noturnos = 15

Os outliers devem representar aproximadamente 4% do dataset.

REQUISITOS IMPORTANTES:

- NÃO gerar dados totalmente aleatórios.
- As variáveis devem possuir dependências probabilísticas coerentes.
- Os dados devem parecer provenientes de um experimento observacional real.
- Os perfis comportamentais devem influenciar múltiplos atributos simultaneamente.
- O dataset deve ser adequado para:
    - classificação supervisionada
    - análise exploratória
    - detecção de outliers
    - tratamento de dados faltantes
    - análise de correlação

FORMATO DE SAÍDA: CSV
```
## Versão 2.5
Para fins de comparação foi elaborado um prompit para geração de atributos feito pelo Claude
```
Gere um dataset sintético em formato [arff] contendo [500] usuários de smartphone para um experimento de aprendizado de máquina voltado à predição da qualidade do sono. Os dados devem simular comportamentos digitais e hábitos de vida relacionados à qualidade do sono, permitindo treinamento e avaliação de modelos de classificação supervisionada.

O DATASET DEVE CONTER:

- mais de 5 atributos
- pelos menos 500 instancias
- pelo menos 1 atributo irrelevante

REGRAS SEMÂNTICAS E HIPÓTESES:

1. Usuários com:
    
    - muitas horas de uso diário,
    - pouco tempo de sono,
    - tempo alto em redes sociais,
    - uso frequente durante a madrugada,
    - alta quantidade de notificações,
    - estresse elevado,
    - insônia, devem possuir maior probabilidade da classe: -> qualidade_sono = ruim
2. Usuários com:
    
    - atividade física moderada ou alta,
    - sono regular,
    - baixo uso noturno,
    - poucas interrupções noturnas,
    - menor tempo em redes sociais, devem possuir maior probabilidade da classe: -> qualidade_sono = bom
3. O dataset deve conter diferentes perfis comportamentais sintéticos, por exemplo:
    
    - usuário saudável
    - estudante universitario
    - heavy user
    - gamer noturno
    - trabalhador corporativo
    - usuário compulsivo de redes sociais
4. As distribuições NÃO devem ser uniformes. Gere padrões realistas e heterogêneos.
    

VALORES FALTANTES: Os valores faltantes devem simular:

- falhas de sensores
- formulários incompletos
- perda de coleta

INSERÇÃO RUÍDOS: Inclua pequenas quantidades de dados inconsistentes simulando erros de entrada e coleta.

INSERÇÃO DE OUTLIERS: Inclua usuários extremos, porém plausíveis, para enriquecer análises estatísticas e testes de robustez.

REQUISITOS IMPORTANTES:

- NÃO gerar dados totalmente aleatórios.
- As variáveis devem possuir dependências probabilísticas coerentes.
- Os dados devem parecer provenientes de um experimento observacional real.
- Os perfis comportamentais devem influenciar múltiplos atributos simultaneamente.
- O dataset deve ser adequado para:
    - classificação supervisionada
    - análise exploratória
    - detecção de outliers
    - tratamento de dados faltantes
    - análise de correlação

FORMATO DE SAÍDA: arff
```