# Justificativas das ações tomadas 

### Remoção da coluna de Poluente_2
Ao estudar a porcentagem de valores nulos que cada coluna possui, chegamos na seguinte tabela:

| Coluna        | Porcentagem |
|---------------|------------|
| `Date`        | 1.203674 |
| `Time`        | 1.203674|
| `CO`          | 18.973709 |
| `Poluente_1`  | 5.068103 |
| `Poluente_2`  | 90.349488|
| `Poluente_3`  | 5.068103|
| `Poluente_4`  | 5.068103|
| `Poluente_5`  | 18.509133|
| `Poluente_6`  | 5.068103|
| `Poluente_7`  | 18.540809|
| `Poluente_8`  | 5.068103|
| `Poluente_9`  | 5.068103|
| `T`           | 5.068103|
| `RH`          | 5.068103|
| `AH`          | 5.068103|

Devido a quantidade de valores nulos de Poluente_2, essa coluna é descartada

# Criação de variáveis e remoção de colunas

Ao avaliar a matriz de correlação das variáveis, entende-se que as medidas de alguns sensores possuem alta correlação entre sí. Como exemplo é possível citar os sensores 3 e 4, os quais apresentam uma correlação de 0.98. Por isso, optou-se por adicionar uma coluna da razão Poluente_3 / Poluente_4 e remover a coluna do P4. Além disso, avaliou-se a utilização de um produto de AH com outras variáveis com baixa correlação com CO, como modificar o produto do enunciado para o produto de AH, RH e T, mas os resultados não foram benéficos ao erro médio.

# Problemas do modelo
Por fim, foi identificado que o modelo possui a tendência de, quando o valor real de CO diminui comparado ao anterior, prever uma variação muito maior do que a real, chegando a prever valores negativos para a concentração, o que é irreal. Para tentar solucionar esse problema, foi testada a previsão não do valor de CO, mas do $ln(CO)$, porém isso resultou em falhas das previsões quando os valores reais de CO se aproximavam de 0, então a ideia foi descartada. 