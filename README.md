# 🔭 Detecção de Exoplanetas com Box Least Squares (BLS)

Este repositório contém o código-fonte e a análise desenvolvida para o Trabalho de Conclusão de Curso (TCC) focado na detecção de trânsitos de exoplanetas.

O projeto implementa o algoritmo **Box Least Squares (BLS)** para analisar curvas de luz de estrelas (como as do telescópio Kepler) e identificar quedas periódicas no brilho, que indicam a passagem de um planeta.

O notebook (`BLS_TCC.ipynb`) demonstra o processo completo: da aquisição dos dados até a análise e visualização dos resultados para o alvo **Kepler-423 b**.

## 💻 Tecnologias Utilizadas

Para executar esta análise, são necessárias as seguintes bibliotecas Python:

* **lightkurve:** Usada para buscar, baixar e processar os dados de curva de luz do Kepler/TESS.
* **astropy:** Utilizada para a implementação do algoritmo Box Least Squares.
* **numpy:** Para manipulação de arrays.
* **matplotlib:** Para a visualização dos gráficos.

A principal dependência pode ser instalada via pip:
```bash
pip install lightkurve
```

## 🚀 Como Executar

Você pode executar esta análise de duas formas:

### Opção 1: Google Colab (Recomendado)

A forma mais simples, pois a maioria das bibliotecas já está pré-instalada no ambiente.

1.  Clique no link abaixo para abrir o notebook diretamente no Colab:

    [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DaviMartinsF/Deteccao-Box-Least-Square/blob/main/BLS_TCC.ipynb)

2.  Execute a primeira célula (que contém `!pip install lightkurve`).
3.  Execute as células restantes na ordem para ver a análise.

---

### Opção 2: Ambiente Local (Jupyter Notebook / Anaconda)

Se você preferir executar o projeto na sua própria máquina, siga estes passos:

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/DaviMartinsF/Deteccao-Box-Least-Square.git](https://github.com/DaviMartinsF/Deteccao-Box-Least-Square.git)
    cd Deteccao-Box-Least-Square
    ```

2.  **Instale as dependências:**
    Se estiver usando o Anaconda, é recomendado criar um novo ambiente. A principal dependência é o `lightkurve` (que já instalará `astropy`, `numpy`, etc.):
    ```bash
    pip install lightkurve
    ```

3.  **Inicie o Jupyter:**
    ```bash
    jupyter notebook
    ```

4.  No seu navegador, clique no arquivo `BLS_TCC.ipynb` para abri-lo e execute as células na ordem.



## 📊 O Processo no Notebook

O notebook está dividido nas seguintes etapas:

* **Instalação:** A primeira célula instala o `lightkurve`.
* **Aquisição de Dados:** O alvo (`Kepler-423 b`) é definido. O `lightkurve` busca e baixa os dados de curva de luz ("light curve") do Kepler. Os dados são então normalizados e valores nulos (NaNs) são removidos.
* **Análise BLS:** O algoritmo `BoxLeastSquares` da `astropy` é aplicado aos dados para encontrar o período orbital, a duração e a profundidade do trânsito planetário.
* **Impressão de Resultados:** Os parâmetros encontrados pelo algoritmo são impressos:
    > ```
    > ✅ Parâmetros encontrados pelo BLS:
    >     - Período: 2.684966 dias
    >     - Época (t0): 353.465031 BKJD
    >     - Duração: 0.0950 dias (~2.28 horas)
    >     - Profundidade: 0.0160
    > ```
