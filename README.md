## Vamos nos conectar:
[Linkedin](https://www.linkedin.com/in/jeduardosleite/)
---

---

<img width="527" height="342" alt="image" src="https://github.com/user-attachments/assets/5a0247af-8042-44a5-8983-1bcfc05f548c" />


# Objetivo

Predizer o valor do contrato com base em variáveis socioeconômicas e comportamentais utilizando a regressão linear. 

```Regressão linear``` é uma técnica estatística usada para modelar e prever a relação entre uma variável dependente (Y) e uma ou mais variáveis independentes (X), assumindo que essa relação pode ser representada por uma linha reta.

# Etapas

### 1) Entendendo o problema
Para este tipo de problema, utilizarei o **aprendizado supervisionado**, aquele em que o modelo aprende a partir de ```dados rotulados```. Existe uma variável alto(*target*) que queremos prever, neste caso, é a ```charges```. Para explicar essa variável, temos: idade, sexo, IMC, número de filhos, região e tabagismo.

Para as **métricas de avaliação**, usarei as seguintes:

- **MAE** (*Mean Absolute Error*): mede o erro médio absoluto entre os valores previstos e reais. Indica, em média, quanto o modelo erra em unidades reais (ex.: reais). Quanto menor o MAE, menor é o erro médio das previsões.
    
- **RMSE** (*Root Mean Squared Error*): mede a raiz do erro quadrático médio, penalizando mais fortemente erros grandes. É indicada quando erros elevados têm maior impacto. Quanto menor o RMSE, melhor o modelo em evitar grandes erros.
    
- **R²** (*Coeficiente de Determinação*): indica a proporção da variabilidade dos dados explicada pelo modelo. Varia geralmente entre 0 e 1 e é útil para comparar o desempenho geral entre modelos.


O ```MAE``` foi adotado como métrica principal por indicar diretamente o erro médio na previsão do valor do plano, alinhando-se ao objetivo do modelo de estimar o custo do contrato de forma clara e interpretável.


### 2) Dataset

Este conjunto de dados contém informações sobre a relação entre atributos pessoais (idade, sexo, IMC, tamanho da família, tabagismo), fatores geográficos e seu impacto nos custos do seguro saúde.

| Variável   | Descrição                                                                 |
|------------|---------------------------------------------------------------------------|
| age      | A idade da pessoa segurada.                                                |
| sex       | Gênero (masculino ou feminino) do segurado.                                |
| bmi        | Índice de Massa Corporal, medida da gordura corporal baseada em peso e altura. |
| children     | Número de dependentes abrangidos pelo seguro.                              |
| smoker    | Indica se o segurado é fumante (sim ou não).                               |
| region     | Área geográfica de cobertura do seguro.                                   |
| charges   | Custos do seguro de saúde incorridos pela pessoa segurada.                |

Para facilitar a interpretação do *BMI* (Índice de Massa Corporal), serão aplicados rótulos que indicam a faixa em que cada valor se enquadra. Inicialmente, essa categorização será utilizada apenas para fins de análise e explicação do negócio, sem a decisão prévia de incluí-la no treinamento do modelo. Ao longo do desenvolvimento do projeto, será avaliada a real necessidade dessa variável com base em seu impacto no desempenho do modelo.

| Faixa de BMI (kg/m²) | Descrição         |
|----------------------|-------------------|
|< 18,5                | Magreza           |
| 18,5 – 24,9          | Normal            |
| 25,0 – 29,9          | Sobrepeso         |
| 30,0 – 39,9          | Obesidade         |
| ≥ 40,0               | Obesidade grave   |

fonte: https://abran.org.br/calculadoras/imc

### 3) EDA (Análise Explanatória de Dados)
1) Verificar os valores nulos, faltantes e a dimensão do dataset;
2) Estatística descritiva (média, mediana, dispersão, quartis etc);
3) Análise de correlação entre as variáveis;
4) Identificação outliers.

### 4) Pré-processamento dos dados
Nesta etapa, será realizada a análise e o tratamento de *outliers*, caso necessário. Em seguida, será feita uma avaliação mais aprofundada das variáveis, com o objetivo de definir quais serão utilizadas no modelo, bem como identificar a necessidade de aplicação de técnicas de *feature engineering* e quais delas serão mais adequadas.

Ao final, será realizada a sepação em treino e teste.

### 5) Modelagem
Com a base separada, está na hora de treinar e comparar diferentes modelos de regressão linear para identificar qual apresenta o melhor desempenho na previsão do valor do plano, considerando erro, estabilidade e capacidade de generalização.

### 6) Avaliação
Após o treinamento, os modelos serão avaliados para verificar qual generaliza melhor para os dados não vistos. Lembrando que a métrica principal será a ```MAE```, porém o *R²* e o *RMSE* serão avaliados também.

### 7) Interpretação dos resultados
Nesta etapa, serão apresentados os resultados obtidos pelo modelo, incluindo a análise da importância das variáveis e o impacto de fatores socioeconômicos e comportamentais. A partir dessas análises, serão extraídos insights relevantes para o negócio.

Além disso, será realizada uma síntese crítica dos resultados, avaliando o desempenho do modelo, suas limitações e possíveis oportunidades de melhoria.

### 8) Aprendizado
Nesta etapa, serão descritos os principais desafios enfrentados ao longo do projeto, bem como as soluções adotadas para superá-los, destacando os aprendizados técnicos e analíticos adquiridos durante o desenvolvimento.
