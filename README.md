# Wine Quality Classification — Tech Challenge Fase 2

## Descrição

Projeto desenvolvido como Tech Challenge da Fase 2 da pós-graduação em Data Analytics (POSTECH/FIAP). O objetivo é prever a qualidade de vinhos com base em características físico-químicas, utilizando modelos de machine learning.

A variável alvo foi transformada em classificação binária:
- **1 (Alta Qualidade):** nota maior ou igual a 7
- **0 (Baixa/Média Qualidade):** nota menor que 7

## Dataset

- **Fonte:** [Wine Quality Dataset — Kaggle](https://www.kaggle.com/datasets/yasserh/wine-quality-dataset)
- **Registros:** 1.143 amostras
- **Features:** 11 variáveis físico-químicas (acidez, teor alcoólico, densidade, pH, sulfatos, entre outras)
- **Variável alvo:** `quality_label` (binária)

## Estrutura do Repositório

```
wine-quality-classification/
├── data/               # Dataset original e arquivos de treino/teste
├── notebooks/          # Notebook principal com toda a análise e modelagem
├── src/                # Scripts auxiliares
├── results/            # Gráficos e métricas gerados
├── requirements.txt    # Bibliotecas utilizadas
└── README.md           # Descrição do projeto
```

## Pipeline

1. **Compreensão do problema** — análise da variável alvo e distribuição das classes
2. **EDA — Distribuição e Outliers** — histogramas, boxplots, análise de assimetria e verificação de valores impossíveis
3. **EDA — Correlações** — matriz de correlação, heatmap, identificação de multicolinearidade
4. **Pré-processamento** — normalização com StandardScaler, feature engineering e train/test split (80/20)
5. **Balanceamento** — SMOTE aplicado exclusivamente no conjunto de treino
6. **Desenvolvimento dos Modelos** — treinamento de 4 classificadores
7. **Avaliação** — comparação com métricas adequadas ao desbalanceamento
8. **Importância das Features** — análise de quais variáveis mais influenciam a qualidade

## Modelos Utilizados

| Modelo | Descrição |
|---|---|
| Regressão Logística | Modelo linear simples, utilizado como baseline |
| Random Forest | Ensemble de árvores de decisão, robusto ao desbalanceamento |
| Gradient Boosting | Boosting sequencial com correção progressiva de erros |
| KNN | Classificação por similaridade com os k vizinhos mais próximos |

## Resultados

O **Gradient Boosting** apresentou o melhor desempenho geral:

| Modelo | F1-Score | AUC-ROC | Recall |
|---|---|---|---|
| Regressão Logística | 0,49 | 0,86 | 0,71 |
| Random Forest | 0,67 | 0,94 | 0,77 |
| **Gradient Boosting** | **0,69** | **0,93** | **0,74** |
| KNN | 0,55 | 0,87 | 0,81 |

> F1-Score e AUC-ROC foram as métricas prioritárias por conta do desbalanceamento das classes (86% Baixa/Média vs 14% Alta Qualidade).

## Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/joao10010/wine-quality-classification.git
cd wine-quality-classification
```

2. Instale as dependências:
```bash
pip install -r requirements.txt
```

3. Abra o notebook:
```bash
jupyter notebook notebooks/code.ipynb
```

## Grupo 33 — POSTECH Data Analytics

Projeto desenvolvido para a disciplina de Machine Learning Aplicado a Negócios.
# TechChallenge_FIAP-Fase2
# TechChallenge_FIAP-Fase2
