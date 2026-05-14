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