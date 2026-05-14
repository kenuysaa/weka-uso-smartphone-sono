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