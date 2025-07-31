# README — Análise de Churn de Clientes com Machine Learning

## Descrição do Projeto

Este projeto tem como objetivo prever o **churn** (cancelamento) de clientes em uma empresa de telecomunicações utilizando técnicas de **machine learning**, **pré-processamento de dados** e **balanceamento de classes**.

A partir do dataset Telco Customer Churn, aplicamos limpeza, transformação, normalização, técnicas para lidar com desbalanceamento, e testamos diferentes modelos para identificar quais entregam melhor desempenho, com foco em métricas relevantes para problemas de churn, como **recall**.

## Tecnologias e Bibliotecas Utilizadas

* Python 3.x
* Pandas e NumPy para manipulação de dados
* scikit-learn para modelagem e avaliação
* imbalanced-learn para técnicas de oversampling (SMOTE)
* Modelos: Regressão Logística e Random Forest

## Passo a Passo do Projeto

1. **Carga e exploração dos dados**

   * Dataset carregado diretamente do repositório IBM no GitHub.
   * Análise inicial para conhecer formato, tipos e distribuição da variável alvo (Churn).

2. **Tratamento e limpeza**

   * Substituição de espaços vazios por valores nulos.
   * Remoção de registros com dados faltantes.
   * Codificação de variáveis categóricas usando Label Encoding.

3. **Separação em features (X) e target (y)**

   * Remoção de identificadores (customerID).
   * Mapeamento do target para valores binários (0 e 1).

4. **Divisão em treino e teste**

   * 70% dos dados para treino e 30% para teste, com stratificação para preservar proporção de churn.

5. **Normalização dos dados**

   * Aplicação do StandardScaler para padronização das features.

6. **Treinamento e avaliação de modelos**

   * Modelo base: Regressão Logística.
   * Avaliação inicial via relatório de classificação, matriz de confusão e AUC-ROC.

7. **Ajuste de threshold para melhorar recall**

   * Mudança do threshold de decisão para 0.3 para aumentar a captura de churners.

8. **Balanceamento de classes com SMOTE**

   * Aplicação de oversampling para corrigir desbalanceamento do target no conjunto de treino.
   * Novo treinamento da Regressão Logística e avaliação.

9. **Comparação com Random Forest**

   * Treinamento de modelo Random Forest no conjunto original.
   * Avaliação dos resultados para comparação com o modelo linear.

## Resultados Obtidos

* A aplicação do ajuste de threshold e balanceamento melhorou significativamente o recall para a classe churn, um ponto crítico para retenção de clientes.
* O modelo Random Forest também apresentou bom desempenho, podendo ser explorado para ganho adicional.
* O uso de técnicas de pré-processamento, como normalização e balanceamento, é essencial para melhorar a performance em datasets desbalanceados.

## Como Executar

1. Instale as dependências:

```bash
pip install pandas numpy scikit-learn imbalanced-learn
```

2. Execute o código em um ambiente Jupyter Notebook ou IDE de sua preferência.


## Possíveis Extensões

* Experimentar outros modelos, como XGBoost, SVM ou Redes Neurais.
* Realizar tuning de hiperparâmetros com Grid Search ou Random Search.
* Implementar visualizações das métricas (curva ROC, precision-recall).
* Avaliar impacto econômico dos falsos positivos e falsos negativos.

Qualquer dúvida ou se quiser que eu te ajude a estruturar o README para um projeto no GitHub com esse código, é só avisar!
