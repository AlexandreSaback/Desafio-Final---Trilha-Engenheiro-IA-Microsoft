# Desafio Final - Trilha Engenheiro IA Microsoft 
Participar desse projeto foi uma oportunidade incrível, sou muito grato aos professores e a todos os organizadores do projeto.

Para resolver os desafios escolhidos, utilizei o laboratório de Machine Learning do Azure.

# Desafio 1  - (3 pontos) Existe alguma correlação entre as notas das provas objetivas? Comente.

Para resolver tal desafio utilizei o designer de pipelines de Machine Learning do Azure para criar um pipeline de pré-processamento de dados e treino do modelo de ML. Dessa forma, realizei a previsão das notas de ciências da natureza utilizando um modelo de regressão linear simples, o qual foi treinado apenas com a variável `NU_NOTA_MT` (nota da prova de matemática). 

![Pipeline](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio1/PipelineDesafio1.png)

O modelo foi treinado com 70% dos dados, o restante foi utilizado para validação. 

## Previsões
![Predictions](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio1/PredictionsDesafio1.png)


## Avaliação
O resultado foi bem interessante, visto que o modelo conseguiu atingir uma pontuação alta de r2 (coeficiente de determinação):
![r2](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio1/r2Desafio1.png)


# Desafio 3 - (3 pontos) Clusterizando os dados do ENADE.

Para resolver tal desafio utilizei novamente o designer de pipelines de Machine Learning do Azure para criar um pipeline de pré-processamento de dados e treino do modelo de ML. Assim, realizei o agrupamento dos alunos em três clusters baseados nas seguintes variáveis: `QE_I08` (renda) , `QE_I23` (horas de estudo) e  `NT_GER` (nota geral).  O modelo de _clusterização_ utilizado foi o `K-means`.

![Pipeline](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio3/PipelineDesafio3.png)
Este modelo também foi treinado com 70% dos dados, o restante foi utilizado para validação. 

## Clusters
![Clusters](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio3/ClustersDesafio3.png)

## Avaliação
![Evaluation](https://raw.githubusercontent.com/AlexandreSaback/Desafio-Final---Trilha-Engenheiro-IA-Microsoft/main/Desafio3/EvaluationDesafio3.png)

A avaliação de um modelo de _clusterização_ é bem diferente da avaliação de um modelo de regressão. As métricas utilizadas foram:

- **Distância Média ao Outro Centro**: indica a proximidade, em média, de cada ponto no cluster aos centroides de todos os outros clusters.
 - **Distância Média ao Centro do Cluster**: indica a proximidade, em média, de cada ponto no cluster ao centroide do cluster.
 -   **Número de Pontos**: o número de pontos atribuídos ao cluster.
 -   **Distância Máxima ao Centro do Cluster**: o máximo das distâncias entre cada ponto e o centroide do cluster desse ponto. Quando esse número é alto, o cluster pode estar altamente disperso. Essa estatística, em conjunto com a  **Distância Média ao Centro do Cluster**, ajuda a determinar o  _espalhamento_  do cluster.
