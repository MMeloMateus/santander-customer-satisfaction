# Santander Customer Satisfaction

Projeto de classificação binária baseado na competição **Santander Customer Satisfaction** do Kaggle (2016).

## Visão Geral

Este projeto utiliza como base o dataset da competição **Santander Customer Satisfaction**, disponibilizada no Kaggle em 2016. O objetivo original da competição é identificar clientes insatisfeitos a partir de centenas de variáveis anonimizadas, permitindo que o banco possa agir de forma antecipada para reduzir churn.

A métrica oficial da competição é a **área sob a curva ROC (ROC_AUC)**, calculada a partir da probabilidade prevista para a variável **TARGET**, que indica se o cliente está satisfeito (`0`) ou insatisfeito (`1`).

🔗 Link da competição:  
https://www.kaggle.com/competitions/santander-customer-satisfaction

---

## Objetivo do Projeto

O objetivo deste projeto é tratar o problema como uma **tarefa de classificação binária**, buscando identificar clientes insatisfeitos a partir das variáveis disponíveis.

A partir das previsões dos modelos, é construído um **cenário hipotético de negócio**, no qual são simulados custos associados a ações de retenção e à perda de clientes. Esses valores são fictícios e servem apenas para permitir a análise sob a ótica de **maximização do lucro esperado por cliente**.

---

## Modelos Avaliados

Foram avaliados os seguintes modelos de machine learning:

- Logistic Regression  
- Random Forest  
- XGBoost  

Os modelos foram comparados em diferentes cenários de pré-processamento:

- Baseline  
- Seleção de Features via agrupamento  
- Redução de dimensionalidade com PCA  

A avaliação foi realizada por meio de **validação cruzada**, utilizando as métricas **ROC_AUC** e **PR_AUC**, sendo esta última especialmente relevante devido ao desbalanceamento da classe positiva.

---

## Conclusão sobre a Seleção do Modelo

Com base nos resultados obtidos nos experimentos de validação cruzada, o modelo selecionado para dar continuidade ao projeto foi o **XGBoost**. Esse modelo apresentou os melhores valores de **ROC_AUC** e **PR_AUC** nos cenários de *Baseline* e *Seleção de Features*.

No cenário em que o **PCA** foi utilizado como etapa de pré-processamento, observou-se uma queda de performance do XGBoost. Esse comportamento pode estar relacionado ao fato de o algoritmo utilizar árvores de decisão combinadas por *gradient boosting*, apresentando melhor desempenho quando as variáveis mantêm maior distinção e significado semântico em sua forma original.

---

## Dependências

As bibliotecas utilizadas no projeto estão listadas no arquivo `requirements.txt`. Caso necessário, podem ser instaladas manualmente:

```bash
pip install numpy
pip install seaborn
pip install scikit-learn
pip install scipy
pip install factor_analyzer
pip install matplotlib
pip install catboost
pip install graphviz
pip install plotly
pip install six
pip install shap-selection
````

---

## Referência

Soraya Jimenez; Will Cukierski.
**Santander Customer Satisfaction**. Kaggle, 2016.
[https://www.kaggle.com/competitions/santander-customer-satisfaction](https://www.kaggle.com/competitions/santander-customer-satisfaction)
