# Atividade de Machine Learning

Notebook com duas etapas de aprendizado supervisionado em Python:

1. **Classificação** de tumores de mama (benigno x maligno) com Regressão Logística, usando o dataset Breast Cancer Wisconsin.
2. **Regressão Linear** para prever o valor de imóveis, usando o dataset California Housing.

Tudo está em `Atividade_ML_Vinicius.ipynb`, já salvo com as saídas e os gráficos, então dá para ler direto pelo GitHub sem executar nada.

## Como executar

Precisa de Python 3.10 ou mais novo. Na primeira execução é necessário estar conectado à internet, porque o scikit-learn baixa o California Housing (o Breast Cancer já vem na biblioteca).

### Só com Python (pip)

```bash
python -m venv .venv
source .venv/bin/activate        # no Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab Atividade_ML_Vinicius.ipynb
```

### Com conda

```bash
conda env create -f environment.yml
conda activate atividade-ml
jupyter lab Atividade_ML_Vinicius.ipynb
```

No Jupyter Lab, use *Kernel > Restart Kernel and Run All Cells* para rodar do início ao fim. Leva poucos segundos.

Os gráficos usam tema escuro por conta própria. Para deixar o restante da interface escuro também: *Settings > Theme > JupyterLab Dark*.

## Resultados (conjunto de teste)

| Parte | Modelo | Métricas |
|---|---|---|
| Classificação | Regressão Logística | Accuracy 0,965 · Precision 0,975 · Recall 0,929 · F1 0,951 (classe maligna) |
| Regressão | Regressão Linear | MAE 0,533 · MSE 0,556 · RMSE 0,746 · R² 0,576 |

A análise desses números, incluindo as limitações de cada modelo, está no próprio notebook.

## Arquivos

- `Atividade_ML_Vinicius.ipynb`: o trabalho
- `requirements.txt`: dependências para instalar com pip
- `environment.yml`: ambiente conda
