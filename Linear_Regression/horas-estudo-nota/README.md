# Linear Regression — Horas Estudadas x Nota

Projeto de estudo de Machine Learning usando **regressão linear simples** para prever a nota de uma prova a partir do número de horas estudadas. Contém duas versões do modelo, cada uma demonstrando um conceito diferente do fluxo de trabalho de ML.

## 📁 Arquivos

| Arquivo | Descrição |
|---|---|
| `main.py` | Treina o modelo com **todos** os dados disponíveis e faz uma previsão pontual. |
| `main2.py` | Separa os dados em **treino e teste** (`train_test_split`) e avalia a qualidade do modelo com o **R²**. |

## 🧠 Sobre o problema

Os dados relacionam:
- **X (feature):** horas estudadas
- **y (target):** nota obtida na prova (0 a 100)

O objetivo é ajustar uma reta que descreva essa relação e, a partir dela, prever notas para novos valores de horas estudadas.

## 📦 Bibliotecas utilizadas

| Biblioteca | Uso no projeto |
|---|---|
| [`numpy`](https://numpy.org/) | Criação e manipulação dos arrays de dados (`time_studied`, `scores`) e geração de pontos para a reta de regressão (`np.linspace`). |
| [`matplotlib`](https://matplotlib.org/) | Plotagem do gráfico de dispersão dos dados reais e da reta de regressão ajustada. |
| [`scikit-learn`](https://scikit-learn.org/) | Implementação do modelo (`LinearRegression`) e, em `main2.py`, da divisão treino/teste (`train_test_split`). |

## ▶️ Como rodar

1. Crie e ative um ambiente virtual (recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux/Mac
   venv\Scripts\activate      # Windows
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute qualquer um dos scripts:
   ```bash
   python main.py
   python main2.py
   ```

Cada script abre uma janela com o gráfico da reta de regressão sobre os dados.

## 🔍 Detalhes de cada script

### `main.py`
- Treina o modelo com **100% dos dados** (não há separação treino/teste).
- Faz uma previsão pontual: nota esperada para quem estudou 56 horas.
- Plota os dados reais + a reta ajustada, com eixo Y fixo entre 0 e 100.
- **Limitação:** como o modelo é avaliado nos mesmos dados usados no treino, não é possível saber se ele generaliza bem para dados novos.

### `main2.py`
- Usa `train_test_split` para dividir os dados em **80% treino / 20% teste**.
- Treina o modelo apenas com o conjunto de treino.
- Avalia o modelo no conjunto de teste usando `.score()`, que retorna o **R² (coeficiente de determinação)** — quanto mais próximo de 1, melhor o modelo explica a variação dos dados.
- Plota apenas os pontos de treino junto com a reta ajustada.

## 📈 Próximos passos (ideias de evolução)

- Adicionar métricas extras como MAE e RMSE.
- Plotar também os pontos de teste no gráfico, diferenciando por cor.
- Testar regressão polinomial para capturar relações não lineares.
- Salvar o modelo treinado com `joblib` ou `pickle`.

---

📚 Projeto feito para estudo de Machine Learning com Python e scikit-learn.