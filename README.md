# Previsão de Risco de Crédito - Statlog (German Credit Data) 

Este repositório contém um projeto focado na classificação e previsão de risco de crédito utilizando a base de dados Statlog (German Credit Data) do UCI Machine Learning Repository.

##  Objetivo
O principal objetivo é construir, avaliar e otimizar diferentes modelos de classificação para identificar se um cliente representa um "bom" ou "mau" risco de crédito. O diferencial analítico deste projeto é a incorporação de uma **matriz de custo** focada no impacto financeiro real das previsões.

##  O Problema de Negócio e a Matriz de Custo
No contexto de concessão de crédito, os erros de previsão não possuem o mesmo peso:
- **Falso Negativo (Negar crédito para um bom cliente):** Gera um custo de oportunidade de peso **1**.
- **Falso Positivo (Liberar crédito para um cliente de alto risco):** Gera risco de inadimplência e prejuízo elevado, com peso **5**.

Portanto, o sucesso dos modelos neste projeto não é avaliado apenas pela acurácia geral, mas sim pela eficácia em minimizar o custo total dos erros de classificação.

##  Tecnologias e Bibliotecas
- **Linguagem:** Python
- **Manipulação e Análise de Dados:** `pandas`, `numpy`
- **Visualização:** `matplotlib`
- **Machine Learning (Scikit-Learn):**
  - **Pré-processamento:** `StandardScaler`, `OneHotEncoder`, `ColumnTransformer`, `Pipeline`
  - **Modelos:** `LogisticRegression`, `DecisionTreeClassifier`, `RandomForestClassifier`, `GradientBoostingClassifier`
  - **Avaliação:** `accuracy_score`, `precision_score`, `recall_score`, `f1_score`, `roc_auc_score`, Matriz de Confusão e Curva ROC.
  - **Otimização:** `GridSearchCV`, Ajuste de Limiar de Decisão (Threshold).

##  Estrutura e Etapas do Projeto
1. **Análise Exploratória de Dados (EDA):** Compreensão das distribuições e tratamento da variável alvo (0 = bom risco, 1 = mau risco).
2. **Pipelines de Pré-processamento:** Criação de fluxos automatizados para tratamento e padronização simultânea de variáveis numéricas e categóricas.
3. **Treinamento e Avaliação de Modelos:** Construção dos algoritmos e criação de uma função de avaliação personalizada focada na matriz de custos financeiros.
4. **Otimização de Modelos:** - Busca de hiperparâmetros com validação cruzada (`GridSearchCV`) aplicada ao Random Forest.
   - Ajuste estratégico do limiar de decisão das probabilidades preditas para minimizar os prejuízos.
5. **Importância das Variáveis (Feature Importance):** Extração e análise dos fatores que mais impactam as decisões de risco dos clientes.

