# Atividade de Machine Learning: classificação e regressão

Notebook da atividade de Machine Learning com dois problemas:

- **Parte 1, classificação:** diagnóstico de tumores de mama (benigno ou maligno) com o dataset *Breast Cancer Wisconsin*.
- **Parte 2, regressão:** previsão do valor de imóveis com Regressão Linear usando o *California Housing*.

O trabalho está todo em [`Atividade_ML_Vinicius.ipynb`](Atividade_ML_Vinicius.ipynb), que já está salvo com as saídas. Dá para ler direto no GitHub sem rodar nada.

## Resultados principais

| Problema | Modelo | Resultado no conjunto de teste |
|---|---|---|
| Classificação | Regressão Logística (com padronização) | Accuracy 0,965 · Precision 0,975 · Recall 0,929 · F1 0,951 |
| Classificação | mesma, com limiar ajustado para 0,30 | Accuracy 0,982 · Recall 0,976 (falsos negativos: 3 → 1) |
| Regressão | Regressão Linear | MAE 0,533 · MSE 0,556 · RMSE 0,746 · R² 0,576 |

A discussão dos resultados e das limitações está nas seções 7 e 8 do notebook.

## Como rodar

### Opção 1: conda / Miniforge

```bash
conda env create -f environment.yml
conda activate atividade-ml
jupyter lab
```

Depois é só abrir `Atividade_ML_Vinicius.ipynb` e usar **Run → Run All Cells**.

### Opção 2: só com Python instalado (pip)

Precisa de Python 3.10 ou mais recente.

**Windows (PowerShell ou Prompt de Comando):**

```bat
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Se o PowerShell bloquear o `activate`, rode antes `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, ou use o Prompt de Comando.

**Linux / macOS:**

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

## Observações

- **Dados:** o *Breast Cancer Wisconsin* já vem com o scikit-learn. O *California Housing* é baixado pelo scikit-learn na primeira execução. Se não houver internet, ou se o download falhar, o notebook usa automaticamente a cópia em `dados/california_housing.csv`, que é idêntica à versão do scikit-learn.
- **Tema escuro:** todos os gráficos do notebook usam um tema escuro próprio. Se quiser o JupyterLab inteiro escuro também, vá em **Settings → Theme → JupyterLab Dark**.
- **Reprodutibilidade:** todas as etapas aleatórias usam `SEED = 42`, então os números se repetem a cada execução.
- **Versões testadas:** Python 3.12 (conda) e 3.13 (pip) com scikit-learn 1.9, pandas 3.1 e JupyterLab 4.6. Também testei com as versões mínimas do `requirements.txt` (Python 3.10, scikit-learn 1.3, pandas 2.0).

## Estrutura

```
.
├── Atividade_ML_Vinicius.ipynb   # notebook com as duas partes
├── dados/
│   └── california_housing.csv    # cópia local do California Housing (fallback)
├── environment.yml               # ambiente conda
├── requirements.txt              # dependências para pip
└── README.md
```
