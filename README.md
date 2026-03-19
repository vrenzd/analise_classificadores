# 🍺 Análise de Classificadores — Dados de Cerveja

Projeto de **classificação binária** que compara quatro algoritmos de Machine Learning para prever a aprovação de cervejas com base em sua nota (nota > 5 = aprovado).

---

## 📁 Estrutura do Projeto

```
.
├── analise_classificadores.ipynb   # Notebook principal com toda a análise
├── data/
│   └── dados_cerveja_nota.xlsx     # Dataset original (opcional)
└── README.md
```

---

##  Objetivo

Treinar e comparar os seguintes modelos de classificação:

| # | Modelo |
|---|--------|
| 1 | Naive Bayes (GaussianNB) |
| 2 | Regressão Logística |
| 3 | Árvore de Decisão — FULL |
| 4 | Árvore de Decisão — 2 Níveis (`max_depth=2`) |

---

##  Dataset

- **15 observações** com as colunas `id`, `cerveja` e `nota`
- **Variável alvo criada**: `aprovado = 1` se `nota > 5`, caso contrário `0`
- Distribuição: 9 aprovados / 6 reprovados

---

##  Requisitos

**Python 3.8+**

Instale as dependências com:

```bash
pip install -r requirements.txt
```

Ou via `conda`:

```bash
conda install -r requirements.txt
```

---

##  Como Executar

1. Clone o repositório ou baixe os arquivos
2. Instale as dependências acima
3. Abra o notebook:

```bash
jupyter notebook analise_classificadores.ipynb
```

4. Execute as células em ordem (`Shift + Enter` ou *Run All*)

> **Nota:** o dataset está embutido diretamente no notebook. Caso prefira carregar o arquivo Excel, descomente a linha `df = pd.read_excel(...)` na célula correspondente.

---

##  Resultados

| Modelo | Acurácia | AUC-ROC | FP | FN |
|---|---|---|---|---|
| Naive Bayes | 86,67% | 0,9722 | 1 | 1 |
| Regressão Logística | 86,67% | 0,9722 | 1 | 1 |
| Árvore Full | **93,33%** | **0,9907** | 0 | 1 |
| Árvore D2 (depth=2) | **93,33%** | 0,9815 | 0 | 1 |

###  Melhor Modelo

A **Árvore de Decisão com max_depth=2** oferece o melhor equilíbrio entre desempenho e interpretabilidade:
- Mesma acurácia da Árvore Full (93,33%)
- Menor risco de *overfitting*
- Estrutura simples e altamente interpretável

---

##  Métricas Utilizadas

- **Acurácia** — proporção de predições corretas
- **AUC-ROC** — área sob a curva ROC (capacidade discriminativa)
- **Matriz de Confusão** — TP, TN, FP, FN
- **Precision / Recall / F1-score** por classe

---

##  Visualizações Geradas

- Comparação geral das probabilidades estimadas por modelo
- Subplots individuais com curva de probabilidade e predição por modelo
- Matrizes de confusão lado a lado
- Diagrama das árvores de decisão (Full e D2)


